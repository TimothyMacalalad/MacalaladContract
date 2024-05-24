event MemberRegistered(address indexed member);
event MemberUnregistered(address indexed member);

function register() public {
    require(!members[msg.sender], "Member already registered");
    
    members[msg.sender] = true;
    memberAddresses.push(msg.sender);
    
    emit MemberRegistered(msg.sender);
}
