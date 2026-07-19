
tar xzf actions-runner-osx-arm64-2.335.1.tar.gz
./config.sh --url https://github.com/lgabraham/healthos --token <A44S3ZMOPZVM6Q2653OAX2LKLROL2> --labels m1 --unattended
./svc.sh install && ./svc.sh start

./config.sh --url https://github.com/lgabraham/healthos --token A44S3ZMOPZVM6Q2653OAX2LKLROL2