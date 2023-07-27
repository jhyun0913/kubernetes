# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/focal64"
    config.vm.define "ctrl" do |ctrl|
        ctrl.vm.hostname = "kube-controller"
        ctrl.vm.provider "virtualbox" do |vb|
            vb.name = "kube-controller"
            vb.cpus = 4
            vb.memory = 8192
        end
        ctrl.vm.network "private_network", ip: "192.168.10.11"
    end

    config.vm.define "wn1" do |wn1|
        wn1.vm.hostname = "kube-worker-node1"
        wn1.vm.provider "virtualbox" do |vb|
            vb.name = "kube-worker-node1"
            vb.cpus = 4
            vb.memory = 4096
        end
        wn1.vm.network "private_network", ip: "192.168.10.12"
    end

    config.vm.define "wn2" do |wn2|
        wn2.vm.hostname = "kube-worker-node2"
        wn2.vm.provider "virtualbox" do |vb|
            vb.name = "kube-worker-node2"
            vb.cpus = 4
            vb.memory = 4096
        end
        wn2.vm.network "private_network", ip: "192.168.10.13"
    end

    #nginx loadbalance 기능 사용해서 NodePort로 공개된 모든 노드가 서비스가 되도록 해보기.
    #pubilc network로 옆 사람과 서로 웹페이지 나오는지 확인해보기
    #할 수 있으면 이전에 static web template도 시도
    config.vm.define "dock" do |dock|
        dock.vm.hostname = "dock-registry"
        dock.vm.provider "virtualbox" do |vb|
            vb.name = "dock-registry"
            vb.cpus = 4
            vb.memory = 4096
        end
        dock.vm.network "private_network", ip: "192.168.10.14"
        dock.vm.network "public_network"
    end

end