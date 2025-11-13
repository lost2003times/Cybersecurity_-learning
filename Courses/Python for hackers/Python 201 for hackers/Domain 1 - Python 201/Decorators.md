___
## Without Arguments

### Input
```
from datetime import datetime
import time

def logger(func):
    def wrapper():
        print("-"*50)
        print("> Execution started {}".format(datetime.today().strftime("%Y-%m-%d %H:%M:%S")))
        func()
        print("> Execution completed {}".format(datetime.today().strftime("%Y-%m-%d %H:%M:%S")))
        print("-"*50)
    return wrapper

@logger

def demo_function():
    print("Execution task!")
    time.sleep(3)
    print("Task Completed!")

demo_function()

logger(demo_function())
```

### Output
```
J:\Python 201 for Hackers>python Decorators.py
--------------------------------------------------
> Execution started 2025-11-12 20:22:23
Execution task!
Task Completed!
> Execution completed 2025-11-12 20:22:26
--------------------------------------------------
--------------------------------------------------
> Execution started 2025-11-12 20:22:26
Execution task!
Task Completed!
> Execution completed 2025-11-12 20:22:29
--------------------------------------------------
```


## With Arguments

### Input
```
import datetime from datetime
import time

def logger_args(func):
    def wrapper(*args, **kwargs):
        print("-"*50)
        print("> Execution started {}".format(datetime.today().strftime("%Y-%m-%d %H:%M:%S")))
        func(*args, **kwargs)
        print("> Execution completed {}".format(datetime.today().strftime("%Y-%m-%d %H:%M:%S")))
        print("-"*50)
    return wrapper

@logger_args
def demo_function_args(sleep_time):
    print("Executing task!")
    time.sleep(sleep_time)
    print("Task Completed!")

demo_function_args(1)
demo_function_args(2)
demo_function_args(3)
```

### Output
```
J:\Python 201 for Hackers>python Decorators.py
--------------------------------------------------
> Execution started 2025-11-12 20:27:44
Executing task!
Task Completed!
> Execution completed 2025-11-12 20:27:45
--------------------------------------------------
--------------------------------------------------
> Execution started 2025-11-12 20:27:45
Executing task!
Task Completed!
> Execution completed 2025-11-12 20:27:47
--------------------------------------------------
--------------------------------------------------
> Execution started 2025-11-12 20:27:47
Executing task!
Task Completed!
> Execution completed 2025-11-12 20:27:50
--------------------------------------------------
```

