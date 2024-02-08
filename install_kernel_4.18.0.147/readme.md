Follow the Tutorial: https://medium.com/@alexanderyegorov_67403/how-to-compile-kernel-module-for-centos8-78287e9d145a

You will get error in this command: `rpmbuild -bp — target=$(uname -m) kernel.spec`
    
    error: line 42: Unknown tag: define buildid .local
    To resolve this error, you should check line 42 of your kernel.spec file.
    It should be "%define buildid 1"


After `make oldconfig` command select the Default values for new prompts.

After `make menuconfig` command go to Networking support > Networking options > BPF based packet filtering framework (BPFILTER) 

    press 'Y' to make it enable.

Save and exit


type command: `cat .config | grep "BPF"`

    Output should be:
    CONFIG_CGROUP_BPF=y
    CONFIG_BPF=y
    CONFIG_BPF_SYSCALL=y
    CONFIG_BPF_JIT_ALWAYS_ON=y
    CONFIG_NETFILTER_XT_MATCH_BPF=m
    CONFIG_BPFILTER=y
    CONFIG_BPFILTER_UMH=y
    CONFIG_NET_CLS_BPF=m
    CONFIG_NET_ACT_BPF=m
    CONFIG_BPF_JIT=y
    CONFIG_BPF_STREAM_PARSER=y
    CONFIG_LWTUNNEL_BPF=y
    CONFIG_HAVE_EBPF_JIT=y
    CONFIG_BPF_EVENTS=y
    CONFIG_BPF_KPROBE_OVERRIDE=y
    CONFIG_TEST_BPF=m
