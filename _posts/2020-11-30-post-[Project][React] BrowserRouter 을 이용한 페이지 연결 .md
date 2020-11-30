---
title: \[React] BrowserRouter 을 이용한 페이지 연결
excerpt_separator: "<!--more-->"
categories:
  - React
tags:
  - React
  - Nodejs
  
---

# 코드

```

import React from "react";
import ReactDOM from "react-dom";
import { BrowserRouter, Route, Switch, Redirect } from "react-router-dom";



// styles for this kit
import "assets/css/bootstrap.min.css";
import "assets/scss/now-ui-kit.scss";
import "assets/demo/demo.css";
import "assets/demo/nucleo-icons-page-styles.css";

// pages for this kit
import Index from "views/Index.js";
import Imagemasking from "views/examples/Imagemasking.js";
import Imageselect from "views/examples/Imageselect.js";
import Modeling from "views/examples/modeling.js";
import Image_Gallery from "views/examples/gallery.js";


ReactDOM.render(
  <BrowserRouter>
    <Switch>
      <Switch>
        <Route path="/index" render={(props) => <Index {...props} />} />
  
        <Route path="/Imagemasking" render={(props) => <Imagemasking {...props} />} />
        <Route path="/Imageselect" render={(props) => <Imageselect {...props} />} />
        <Route path="/Modeling" render={(props) => <Modeling {...props} />} />
        <Route path="/Image_Gallery" render={(props) => <Image_Gallery {...props} />} /> 


        <Redirect to="/index" />
        <Redirect from="/" to="/index" />
      </Switch>
    </Switch>
  </BrowserRouter>,
  document.getElementById("root")
);


```

# 설명
- ```<Route path="/index" render={(props) => <Index {...props} />} />``` : 해당 path(/index)로 Request이 오면 해당 컴포넌트(Index) 렌더링한다
- ```<Redirect to="/index" />``` : 잘못된 주소로 들어오면 /index로 이동
