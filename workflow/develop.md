# Develop Flow

1. Understand the development requirement from Issue
2. Git feature branch from develop branch, follow branch naming conversion: ***\<category>/(\<reference>|no-ref)_description***
    ````bash
    git checkout -b feature/AP-5_change-default-avatar
    ````
3. Start programming, local test
4. Commit code, follow commit naming conversion: ***type(\<scope>): \<subject>***
    ````bash
    git add .
    git commit -m 'feat/<core>: add avatar package; change default avator in view
    ````
5. Git push local branch to remote
    ````bash
    git push origin feature/AP-5_change-default-avatar
    ````
6. Create Pull requests, and merge
