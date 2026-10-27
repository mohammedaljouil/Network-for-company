# Network-for-company
A complete network topology  for a company that has branches in many cities in Yemen , Sana'a , Taiz , Hodyda,Mukalla, Aden  and in every city there is number of hosts supported according to the number asked also  this topology contain DNS server , DHCP server and TFTP server, the connectivity of this topology has been done using RIP protocol. 


jwt_tool() {
    # إذا تم تمرير رمز (Token) ولم يتم تحديد وضع استغلال معين، يتم إلحاق راية المحرك التفاعلي تلقائياً (-X a)
    if [ $# -eq 1 ] && [[ "$1" =~ ^ey[A-Za-z0-9_-]+\.ey[A-Za-z0-9_-]+\.[A-Za-z0-9_-]+$ ]]; then
        echo -e "\033[1;34m[*] Native JWT detected. Initializing interactive exploit wizard...\033[0m"
        sudo docker run -it --rm \
            -v "$(pwd)":/opt/jwt_tool \
            jwt_tool "$1" -X a
    else
        # في الحالات الأخرى، يتم تمرير جميع المعطيات المكتوبة في الـ CLI بشكل مباشر
        sudo docker run -it --rm \
            -v "$(pwd)":/opt/jwt_tool \
            jwt_tool "$@"
    fi
}
