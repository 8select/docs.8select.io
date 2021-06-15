# User Identification

To enable commission based pricing the user has to be identified with a consistent identifier. The identifier is called `userId` and must be consistent for all events concerning a single user. The identifier should be anonymized, i.e. a generated id without any connection to personal data.  
This has to be done on a best efforts basis. We know that making this work 100% of the time is impossible because users can clear their device cache or change devices or something else to break the consistency.

