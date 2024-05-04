
-> master branch will be on local which currently uses h2. Want to migrate this to postgres? or mysql eventually.
-> then release branches on QA env which uses postgres (this is what FE will use)
->then live

So 
master branch -> has all code and this is what local is pushed to
-> master branch is then deployed to QA when there is a change needed to test on FE. this becomes a release branch every push to qa. so first push will be release 1.0.0
-> when all testing is done and happy with these changes, then this release branch is added to the prod branch.
-> new release branch is create to the qa env.