# Cluster provisioning (Working in Progress)

## Target Enviornment

Rocky Linux 9.3 (in UTM VM in Macos Host Machine)

## TODO

~~ansible 통해서 호스트네임 지정하고, 각 inventory 내의 호스트 별로 실제 머신의 호스트네임 변경할 수 있도록. (그래서 컨트롤플레인/워커노드 각 노드 이름 구분 가능하도록)
/etc/hosts 수정 추가 필요.~~

클러스터 부트스트래핑 이후, 추가적인 워커노드 / 컨트롤플레인 추가 기능 지원

ETCD 를 stacked 형태가 아닌 외부 etcd 를 연결 가능하도록 하는 옵션 지원

기타 미비한 사항 지원
