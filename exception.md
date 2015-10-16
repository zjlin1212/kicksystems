# Exception Control Flow

##Exception
系统中为每种可能的异常都分配了一个唯一的非整数的异常号(exception number),其中一些号码是由处理器的设计者分配的，如divide by zero, page faults, memory access violations, break- points, and arithmetic overflows；另外一些是由os kernel的设计者分配的，如system calls and signals from external I/O devices.

当系统启动时，操作系统会分配和初始化一个jump table,我们称为exception table. table的kth entry(k is exception number)包含address of the handler for exception k. Exception table的地址存放在exception table base register.

An exception is akin to a procedure call, but with some important differences :
1. 如果从用户程序转移到内核, 那么用户程序的状态会被压到**内核栈**中.
2. 异常处理程序运行在**kernel mode**

##不同的异常

###interrupt
中断是异步发生的,是来自处理外部的I/O设备信号的结果.

###trap & system call
trap是有意的异常(active),主动触发.

###fault

###abort