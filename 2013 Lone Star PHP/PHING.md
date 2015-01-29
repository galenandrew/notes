# PHING all the things
@author OMni Adams @omnicolor
@date 2013-06-28
@feedback joind.in/8681

## Misc
- PHP Code Sniffer
- PHPDoc

## Thoughts
- Ignore compiled CSS in repo and compile from SASS during deploy (Capistrano/PHING)
- Developer Toolkit Repo (store deploy scripts here…part of build would pull latest version of deploy scripts)
- Store passwords on server and pull into build

## Deployments
- Minimal Downtime
- Rollback easily
- Deploy from a stable/versioned release
- Tag releases (major.minor.patch|bug)
- Build config during deploy vs storing in repo
- Minify JS/CSS, etc