# pytest-stack

## Source

https://drive.google.com/file/d/1V5WQrPkUPFl2mWzh-dNBwIopzJ9fFhxu/view

## Getting Started

```bash
pipx install pytest
```

## Success

```bash
$ pytest
============================= test session starts =============================
platform win32 -- Python 3.7.9, pytest-7.1.2, pluggy-1.0.0
rootdir: C:\Users\mcs22\Repos\pytest-stack
collected 1 item

ch1\test_one.py .                                                        [100%]

============================== 1 passed in 0.01s ==============================
```

## Verbose Failure

```bash
$ pytest -v
============================= test session starts =============================
platform win32 -- Python 3.7.9, pytest-7.1.2, pluggy-1.0.0 -- C:\Users\mcs22\.local\pipx\venvs\pytest\Scripts\python.exe
cachedir: .pytest_cache
rootdir: C:\Users\mcs22\Repos\pytest-stack
collecting ... collected 1 item

ch1/test_one.py::test_passing FAILED                                     [100%]

================================== FAILURES ===================================
________________________________ test_passing _________________________________

    def test_passing():
>   	assert (4, 2, 3) == (1, 2, 3)
E    assert (4, 2, 3) == (1, 2, 3)
E      At index 0 diff: 4 != 1
E      Full diff:
E      - (1, 2, 3)
E      ?  ^
E      + (4, 2, 3)
E      ?  ^

ch1\test_one.py:2: AssertionError
=========================== short test summary info ===========================
FAILED ch1/test_one.py::test_passing - assert (4, 2, 3) == (1, 2, 3)
============================== 1 failed in 0.01s ==============================
```


check out interesting traceback in pytest test_card_fail.py

```bash
============================= test session starts =============================
platform win32 -- Python 3.7.9, pytest-7.1.2, pluggy-1.0.0
rootdir: C:\Users\mcs22\Repos\pytest-stack\code, configfile: pytest.ini
collected 1 item

test_card_fail.py F                                                      [100%]

================================== FAILURES ===================================
_____________________________ test_equality_fail ______________________________

    def test_equality_fail():
        c1 = Card("sit there", "brian")
        c2 = Card("do something", "okken")
>       assert c1 == c2
E       AssertionError: assert Card(summary=...odo', id=None) == Card(summary=...odo', id=None)
E         
E         Omitting 1 identical items, use -vv to show
E         Differing attributes:
E         ['summary', 'owner']
E         
E         Drill down into differing attribute summary:
E           summary: 'sit there' != 'do something'...
E         
E         ...Full output truncated (8 lines hidden), use '-vv' to show

test_card_fail.py:7: AssertionError
=========================== short test summary info ===========================
FAILED test_card_fail.py::test_equality_fail - AssertionError: assert Card(su...
============================== 1 failed in 0.05s ==============================
```

Page 50