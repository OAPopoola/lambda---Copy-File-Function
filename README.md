# lambda---Copy-File-Function
This is the insides of a lambda function that on activation will copy the file 
uploaded to an s3 bucket to another bucket
It is simplistic because:
Both source and target buckets are known.
Both buckets are in the same account.
It handles 'small' files. 
Large files require a different copy API call to allow for miltipart copy

Notes:
I battled with a 'header not found' error for files that have special characters and spaces in their names
urllib came to my rescue.
Keep in mind also that as this code runs in a lambda function files that require more time to copy than the maximum time a lambda fumction can run will definitely fail
