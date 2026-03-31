<!-- { section: "44381871-6f1f-4b27-9f56-a243cf65646d", x: 0, y: 0} -->

```stack
card ModuleCompleted do
  log("Module 3 Complete")
  # write_result("module3_completed", "yes")

  # 2025-07-09 13:52
  tomorrow_date = datetime_add(now(), 1, "D")
  # 09
  tomorrow_day = day(tomorrow_date)
  # 07
  tomorrow_month = month(tomorrow_date)
  # 2025
  tomorrow_year = year(tomorrow_date)
  # 2025-07-09 00:00
  tomorrow = date(tomorrow_year, tomorrow_month, tomorrow_day)
  # 2025-07-09 08:00
  next_engagement_time = datetime_add(tomorrow, 8, "h")

  update_contact(next_engagement_time: "@next_engagement_time")
end

```