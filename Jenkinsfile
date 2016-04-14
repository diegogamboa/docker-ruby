def image = 'ruby'

parallel (
  '2.1-ubuntu': {
    stage '2.1-ubuntu'
    node {
      checkout scm
      dir('2.1/ubuntu') {
        hoister.imageName = image
        hoister.buildAndPush '2.1-ubuntu'
      }
    }
  },
  '2.2-ubuntu': {
    stage '2.2-ubuntu'
    node {
      checkout scm
      dir('2.2/ubuntu') {
        hoister.imageName = image
        hoister.buildAndPush '2.2-ubuntu'
      }
    }
  }
)

parallel (
  '2.1-debian-nodejs': {
    stage '2.1-debian-nodejs'
    node {
      checkout scm
      dir('2.1/debian/nodejs') {
        hoister.imageName = image
        hoister.buildAndPush '2.1-debian-nodejs'
      }
    }
  },
  '2.1-ubuntu-chrome': {
    stage '2.1-ubuntu-chrome'
    node {
      checkout scm
      dir('2.1/ubuntu/chrome') {
        hoister.imageName = image
        hoister.buildAndPush '2.1-ubuntu-chrome'
      }
    }
  },
  '2.1-ubuntu-firefox': {
    stage '2.1-ubuntu-firefox'
    node {
      checkout scm
      dir('2.1/ubuntu/firefox') {
        hoister.imageName = image
        hoister.buildAndPush '2.1-ubuntu-firefox'
      }
    }
  }
)
