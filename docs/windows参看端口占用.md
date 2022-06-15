# windows参看端口占用


netstat -ano |grep "8001"
  TCP    0.0.0.0:8001           0.0.0.0:0              LISTENING       2392
  TCP    [::]:8001              [::]:0                 LISTENING       2392
  TCP    [::1]:49533            [::1]:8001             TIME_WAIT       0

tasklist|findstr "2392"
  java.exe                      2392 Console                    1     87,252 K

taskkill /T /F /PID 9088 