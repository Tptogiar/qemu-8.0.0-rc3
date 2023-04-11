config:
	cd build && ../../configure --enable-kvm  --target-list=x86_64-softmmu --enable-debug

ci: c i
c:
	cd build && make -j 24
i:
	cd build && make install -j 24


clean:
	cd build && make clean
distclean:
	cd build && make distclean


connectQMP:
	telnet localhost 4444

rcq:
	./build/qemu-system-x86_64 -m 8G \
                -drive format=qcow2,file=/tptogiar/projects/img/centos8.4.21.qcow2 \
                -enable-kvm \
                -chardev socket,id=qmp,port=4444,host=localhost,server=on \
                -mon chardev=qmp,mode=control,pretty=on \
                -vnc 192.168.182.10:68 \
                -monitor stdio
#-cdrom CentOS-8.4.2105-x86_64-dvd1.iso \


