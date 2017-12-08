# LifecycleModel
[ ![Bintray](https://img.shields.io/badge/bintray-v1.0.0-brightgreen.svg) ](https://bintray.com/jessyancoding/maven/lifecyclemodel/1.0.0/link)
[ ![Build Status](https://travis-ci.org/JessYanCoding/LifecycleModel.svg?branch=master) ](https://travis-ci.org/JessYanCoding/LifecycleModel)
[ ![API](https://img.shields.io/badge/API-14%2B-blue.svg?style=flat-square) ](https://developer.android.com/about/versions/android-4.0.html)
[ ![License](http://img.shields.io/badge/License-Apache%202.0-blue.svg?style=flat-square) ](http://www.apache.org/licenses/LICENSE-2.0)

## The LifecycleModel class is designed to store and manage UI-related data in a lifecycle conscious way, The LifecycleModel class allows data to survive configuration changes such as screen rotations,  It also handles the communication of the Activity / Fragment with the rest of the application

## Download
``` gradle
 compile 'me.jessyan:lifecyclemodel:1.0.0'
```

## Usage
### Step 1
```java
 public class UserLifecycleModel implements LifecycleModel {
         private int id;
 
         public UserLifecycleModel(int id) {
             this.id = id;
         }
 
         @Override
         public void onCleared() {
             //release resources
         }
     }
```

### Step 2
```java
 //Put data
 LifecycleModelProviders.of(activity/fragment).put(UserLifecycleModel.class.getName(), new UserLifecycleModel(1));  

 //Get data
 LifecycleModelProviders.of(activity/fragment).get(UserLifecycleModel.class.getName());  
 
 //Remove data
 LifecycleModelProviders.of(activity/fragment).remove(UserLifecycleModel.class.getName());
```


## About Me
* **Email**: <jess.yan.effort@gmail.com>
* **Home**: <http://jessyan.me>
* **掘金**: <https://gold.xitu.io/user/57a9dbd9165abd0061714613>
* **简书**: <http://www.jianshu.com/u/1d0c0bc634db>

## License
```
 Copyright 2017, jessyan

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```