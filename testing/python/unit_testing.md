### Simple Example
```
import pytest

# Production Code
def str_len(theStr):
    return len(theStr)

# A Unit Test
def test_string_length():
    testStr = "1"
    result = str_len(testStr)
    assert result == 1
``` 
