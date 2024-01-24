# Cluster provisioning (Working in Progress)

## Target Enviornment

Rocky Linux 9.3 (in UTM VM in Macos Host Machine with aarch64/arm64 architecture)

## How to test / user it?

1. inventories 내의 yaml 파일을 본인의 환경에 맞게 수정. (ip 주소, 해당 머신들 접근 id/password -> sudoers 여야 함)

2. `playbooks/configs` 내의 master.yaml / worker.yaml 수정. 특히 `worker.yaml` 내의 `apiServerEndpoint` 유의 할 것.

2. `$ ansible-playbook -i inventories/utm.yaml --become --become-user=root playbooks/setup.yaml` 를 통해 클러스터 셋업

## TODO

~~ansible 통해서 호스트네임 지정하고, 각 inventory 내의 호스트 별로 실제 머신의 호스트네임 변경할 수 있도록. (그래서 컨트롤플레인/워커노드 각 노드 이름 구분 가능하도록)
/etc/hosts 수정 추가 필요.~~

클러스터 부트스트래핑 이후, 추가적인 워커노드 / 컨트롤플레인 추가 기능 지원

ETCD 를 stacked 형태가 아닌 외부 etcd 를 연결 가능하도록 하는 옵션 지원

기타 미비한 사항 지원

HA 된 control plane(여러개의 컨트롤플레인 노드) + HAProxy / Keepalived 등의 환경으로 control plane endpoint 가 1개일 경우에 대해서 테스트
+ Keepalived / HAProxy 설정 자동화
