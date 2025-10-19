# Milestone 2

### Cumulative count

I couldn't figure out how to make a cumulative line graph where I am adding up the counts without manipulating the data in polars separately (creating a count variable), so I asked ChatGPT for an example, and this is what it said:

// Example: cumulative count of events over time per category

chart = alt.Chart(data, title="Cumulative Counts Over Time").mark_line().transform_window(
    # Compute cumulative sum
    cumulative='count',
    as_='cumulative_count',
    sort=[alt.SortField('time_field')],
    groupby=['group_field']  # optional: separate lines per group
).encode(
    x=alt.X('time_field:O', title='Time'),          # e.g., 'year' or 'date'
    y=alt.Y('cumulative_count:Q', title='Cumulative Count'),
    color=alt.Color('group_field:N', title='Category')  # optional grouping color
)
