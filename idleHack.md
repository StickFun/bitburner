var target = getHostname();
var moneyThresh = getServerMaxMoney(target) * 0.75;
var securityThresh = getServerMinSecurityLevel(target) + 5;
while (true) {
    if (getServerSecurityLevel(target) > securityThresh) {
        weaken(target);
    } else if (getServerMoneyAvailable(target) < moneyThresh) {
        grow(target);
    } else {
        hack(target);
    }
}
