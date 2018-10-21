+++
categories = ["Java"]
date = "2018-10-21T12:20:01+00:00"
description = ""
draft = true
tags = ["Optional"]
title = "Optional"

+++
### Optional

    String text = getText();
    int length;
    if (text != null) {
    	length = maybeText.get().length();
    } else {
    	length = 0;
    }

는 

    int length = Optional.ofNullable(getText()).map(String::length).orElse(0);

와 같다.