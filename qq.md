```java
long end2 = System.currentTimeMillis();
log.info("缓存结束时间 {}", end2);
session.setAttribute("user", user);//注意：这里是HttpSession
log.info("从缓存中查询数据");
log.info("login success, username: {}, password: {}", name, pwd);
messagingService.sendLoginMessage(LoginMessage.of(user.getEmail(), user.getName(), true));
return "redirect:/base";
