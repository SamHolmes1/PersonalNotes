You need a .catch in the controller(THE CONTROLLER MUST TAKE NEXT AS AN ARG)
The .catch block needs to take err and invoke next with err
and then you use the middleware in the bottom of the app script
the middleware should then send a 400 and an object with a msg key