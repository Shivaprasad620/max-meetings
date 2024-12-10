def maxMeetings(start, end):
    # Number of meetings
    n = len(start)
    
    # Create a list of meetings and sort by end time
    meetings = list(zip(start, end))
    meetings.sort(key=lambda x: x[1])  # Sort by end time
    
    # Initialize the count of meetings and the end time of the last meeting
    count = 1  # The first meeting can always be scheduled
    last_end_time = meetings[0][1]
    
    # Iterate over the rest of the meetings
    for i in range(1, n):
        if meetings[i][0] >= last_end_time:  # If the start time is greater or equal to the last end time
            count += 1  # Increment the count
            last_end_time = meetings[i][1]  # Update the last end time
    
    return count

# Test the function with the given intervals
start_times = [1, 2, 3, 5, 7]
end_times = [4, 5, 6, 8, 9]

# Find the maximum number of meetings in a room
print("Maximum number of meetings in a room:", maxMeetings(start_times, end_times))
