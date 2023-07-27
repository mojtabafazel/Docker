curl -sSL https://get.blockbridge.com/container | sh

Blockbridge Storage Container 4.3.0-5544.1 (01eaaf74-7013-4f5a-87f6-cbd5f7e68ce5)
Mode: converged

Generated Credentials (may not reflect current system state)
=================================================================================
System admin API token:  1/Vt6FWMtnVH2A+hDbaHpaQTH4lJsUXBrUMRp0JRzxOb1G3oVYy2dVPA
System admin username:   system
System admin password:   ae8b075a7cb28d98da2d845929de3b25
Default user username:   default
Default user password:   f10b87156caefac5651f356390a3728a
Volume plugin API token: 1/KAosmocVujB633RPhmCjeusWEsR4X/dn3J33xGYrNYYICiyahxW7cQ
=================================================================================

docker plugin install --alias block blockbridge/volume-plugin 
  BLOCKBRIDGE_API_HOST="127.0.0.1" BLOCKBRIDGE_API_KEY="1/Vt6FWMtnVH2A+hDbaHpaQTH4lJsUXBrUMRp0JRzxOb1G3oVYy2dVPA"


  docker volume create --name test --driver block

  docker run -itd  --name ubuntu --name ubuntu  --volume-driver block  -v test:/root/  ubuntu:latest

