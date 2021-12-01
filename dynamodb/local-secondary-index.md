# Local Secondary Index
# September 21, 2021

I've generally just defaulted to Global Secondary Indexes (GSI) in Dynamo whenever I've needed an index, so I never took the time to even understand the difference between those and
Local Secondary Indexes (LSI).

Key Differences:
- LSIs use the same partition key as the table's primary key
- LSIs must be created at the same time as the table itself 
- LSIs are strongly consistent

