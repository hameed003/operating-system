**Q1**: this is my system's processor configuaration :
| **Property** | **Value** |
|--------------------------|------------------|
| **Base Speed** | 2.30 GHz |
| **Sockets** | 1 |
| **Cores** | 4 |
| **Logical Processors** | 8 |
| **Virtualization** | Enabled |
| **L1 Cache** | 384 KB |
| **L2 Cache** | 2.0 MB |
| **L3 Cache** | 4.0 MB |

can you explain in details what does all these means. [Ans-1]()

**Q2**: `satement 1`: 1 core contains two logical cores,
`statement 2`: 1 core contains contains 2 thread and
`statement 3`: 1 core can handle 2 thread
are all thses 3 statement same. [Ans-2]()

**Q3**: `2 logical cores` and `2 thread` are they both same thing? [Ans-3]()

**Q4**: means `threads` are not already present in the `core` but they are created once a software or application are run/executed. [Ans-4]()

**Q5**: so that means the threds are not executed by the phsical core but it is executed by the logcal cores. [Ans-5]()

**Q6**: since you said the logical cores are created by `technologies like `Hyper-Threading (HT)`so if processoe does not support`HT`, so how it can even contain `4 logical cores`for`4 core process`, should it not only contain `4 physical core` ? [Ans-6]()

**Q7**: what does `logical cores` actually means are they any `program` or what ? [Ans-7]()

**Q8**: is it similar to `virtualization of hardware resources` like we use `Vmware` and `virtaul box` to create multiple `OS` machine. [Ans-8]()

**Q9**: consider a hypothothetical scenario where there is a `system/machine` which contains `4 physical cores` and `8 logiacal cores` and three is no process running on it currently and if i run a `program/softwar` which contains only `one process ( main thread )` and no `child process` or `sub process` ( other threads ), so will there be used only `one logical core`. [Ans-9]()
