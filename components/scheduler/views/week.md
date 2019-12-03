---
title: Week
page_title: Scheduler for Blazor | Week View
description: Week View in the Scheduler for Blazor
slug: scheduler-views-week
tags: telerik,blazor,scheduler,view,week
published: True
position: 1
---

# Week View

The Week view of the scheduler shows the entire week to the user.

The `Date` parameter of the scheduler controls which week is displayed. The first day depends on the current culture's `FirstDayOfWeek`.

In this article:

* [Example](#example)
* [View Parameters](#view-parameters)
	* [Slots](#slots)

>caption Figure: Week View in the scheduler

![](images/week-view-sample.png)

## Example

>caption Declare the Week View in the markup

>tip You can declare other views as well, this example adds only the week view for brevity.

````CSHTML
@* Define the day view. The screenshot above is the result from this code snippet *@

<TelerikScheduler Data="@Appointments" @bind-Date="@StartDate" Height="600px" 
                  StartField="@(nameof(SchedulerAppointment.StartTime))"
                  EndField="@(nameof(SchedulerAppointment.EndTime))"
                  TitleField="@(nameof(SchedulerAppointment.Title))"
                  DescriptionField="@(nameof(SchedulerAppointment.Description))"
                  IsAllDayField="@(nameof(SchedulerAppointment.IsAllDay))">
    <SchedulerViews>
        <SchedulerWeekView StartTime="@DayStart" EndTime="@DayEnd" WorkDayStart="@WorkDayStart" WorkDayEnd="@WorkDayEnd" />
    </SchedulerViews>
</TelerikScheduler>

@code {
    public DateTime StartDate { get; set; } = new DateTime(2019, 11, 29);
    //the time portions are important
    public DateTime DayStart { get; set; } = new DateTime(2000, 1, 1, 8, 0, 0);
    public DateTime DayEnd { get; set; } = new DateTime(2000, 1, 1, 20, 0, 0);
    public DateTime WorkDayStart { get; set; } = new DateTime(2000, 1, 1, 9, 0, 0);
    public DateTime WorkDayEnd { get; set; } = new DateTime(2000, 1, 1, 17, 0, 0);
    List<SchedulerAppointment> Appointments = new List<SchedulerAppointment>()
    {
            new SchedulerAppointment
            {
                Title = "Board meeting",
                Description = "Q4 is coming to a close, review the details.",
                StartTime = new DateTime(2019, 11, 29, 10, 00, 0),
                EndTime = new DateTime(2019, 11, 29, 11, 30, 0)
            },

            new SchedulerAppointment
            {
                Title = "Vet visit",
                Description = "The cat needs vaccinations and her teeth checked.",
                StartTime = new DateTime(2019, 11, 28, 11, 30, 0),
                EndTime = new DateTime(2019, 11, 28, 12, 0, 0)
            },

            new SchedulerAppointment
            {
                Title = "Planning meeting",
                Description = "Kick off the new project.",
                StartTime = new DateTime(2019, 11, 27, 9, 30, 0),
                EndTime = new DateTime(2019, 11, 27, 12, 45, 0)
            },

            new SchedulerAppointment
            {
                Title = "Trip to Hawaii",
                Description = "An unforgettable holiday!",
                IsAllDay = true,
                StartTime = new DateTime(2019, 11, 27),
                EndTime = new DateTime(2019, 12, 07)
            }
    };

    public class SchedulerAppointment
    {
        public string Title { get; set; }
        public string Description { get; set; }
        public DateTime StartTime { get; set; }
        public DateTime EndTime { get; set; }
        public bool IsAllDay { get; set; }
    }
}

````


@[template](/_contentTemplates/scheduler/views.md#day-views-common-properties)

@[template](/_contentTemplates/scheduler/views.md#visible-times-tip)

@[template](/_contentTemplates/scheduler/views.md#day-slots-explanation)


## See Also

  * [Views]({%slug scheduler-views-overview%})
  * [Navigation]({%slug scheduler-navigation%})
  * [Live Demo: Scheduler Week View](https://demos.telerik.com/blazor-ui/scheduler/week-view)
  