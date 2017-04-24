# unix signals
Signals are an interprocess communication mechanism, a signal is an **asynchronous notification** sent to a process or thread to notify it of an event that occured.

When a signal is sent, the OS will interrupt the normal flow of execution of the process, the OS will only interrupt during a **non-atomic instruction**. If the receiver has registered a signal handler, that will receive the signal, otherwise the default signal handler is called.

## Useful signals
* **SIGINT**: indicates that a user is wishing to interrupt the process ie hitting CTRL+C
* **SIGKILL**: tries to terminate the process immediately, this signal cannot be caught or ignored, additionaly the process does not have a chance to perform any cleanup
* **SIGQUIT**: the user has requested the process quite and perform a core dump
* **SIGSTOP**: stop the process for later resumption
* **SIGTERM**: request termination of the process, it CAN be caught and / or ignored unlike SIGKILL

## links
* [Wiki](https://en.wikipedia.org/wiki/Unix_signal
