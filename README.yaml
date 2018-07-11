{
  "swagger" : "2.0",
  "info" : {
    "description" : "<p><b>Hello!</b></p>\n  <p>\n  This guideline on the working with API WebOffice consists of all the necessary instruments for your own Web Office foundation on the base of our development. <br>\n  It includes functions of registration and authorization, profile management and management of trading accounts, asset management usage, Service Desk, CRM work functions and many other things.\n  The examples of realization and lists of parameters are added in documentation for each request. <br>\n  If there are any questions, we will be glad to answer them! You can address them to our Technical Support Team of the UTIP Technologies company.<br>\n  We wish you good luck in the successful projects development!\n  </p>\n  <p><b>How to start:</b></p>\n <P>\n  <ol>\n\t<li> <div style=\"text-decoration: underline\">To adjust a Web Office: </div>\n\t\tIn file \"[WEBOFFICE PATH]\\protected\\config\\local.php\" you need to type a key for API address: \"'ApiKey' => '{mykey}',\"\n\t</li>\n\t<li> <div style=\"text-decoration: underline\">To form API requests in a certain way: </div>\n\t\t<i>In each request you need to transfer 2 parameters:</i>\n    <ul><li>\trand_param. It needs to have from 7 preferred figures or letters</li>\n    <li>\tkey. It needs to have hash signature, which is forming by the next mean: md5({mykey}.{rand_param})</li></ul>\n\t</li>\n\t</ol>\n\t</p>",
    "version" : "2.0",
    "title" : "WEB OFFICE API Documentation",
    "termsOfService" : "",
    "contact" : { }
  },
  "consumes" : [ "application/json" ],
  "produces" : [ "application/json" ],
  "paths" : {
    "/changePassword" : {
      "post" : {
        "summary" : "Password change",
        "description" : "Password change (request returns the success message) (users with any role exclude \"admin\") ",
        "consumes" : [ ],
        "parameters" : [ {
          "name" : "user_id or user_login",
          "in" : "query",
          "required" : true,
          "type" : "string",
          "description" : "identification number of the user in the database of the Personal Office or user login in the database of the Personal Office"
        }, {
          "name" : "new_password",
          "in" : "query",
          "required" : true,
          "type" : "string",
          "description" : "new password"
        }, {
          "name" : "password_repeat",
          "in" : "query",
          "required" : true,
          "type" : "string",
          "description" : "new password"
        }, {
          "name" : "auth_token",
          "in" : "query",
          "required" : true,
          "type" : "string",
          "description" : "key of the user who is sending the request. It is used to determine the right for performing the operation in this request"
        }, {
          "name" : "old_password",
          "in" : "query",
          "required" : false,
          "type" : "string",
          "description" : "old password"
        }, {
          "name" : "activation_key",
          "in" : "query",
          "required" : false,
          "type" : "string",
          "description" : "change password through the activation key (the second step after the GenerateRecoveryPasswordLetter function)"
        }, {
          "name" : "body",
          "in" : "body",
          "required" : true,
          "schema" : {
            "type" : "object"
          },
          "x-examples" : {
            "application/json" : "      $rand_param = rand(1000000, 99999999);\n      $key = md5('dfdf' . $rand_param);\n      $data = http_build_query(array(\n      'key' => $key,\n      'rand_param' => $rand_param,\n      'auth_token' =>'7917f2596f8bb70c954893f200ba6274',\n      'user_login' => 'trader',\n      'new_password' =>'123456',\n      'password_repeat' =>'123456',\n      ));\n      if ($curl = curl_init()) {\n      curl_setopt($curl, CURLOPT_URL, 'http://my.site.com/api/v_2/page/ChangePassword');\n      curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);\n      curl_setopt($curl, CURLOPT_POST, true);\n      curl_setopt($curl, CURLOPT_POSTFIELDS, $data);\n      $out = json_decode(curl_exec($curl), true);\n      curl_close($curl);\n      }\n      var_dump($out);"
          }
        } ],
        "responses" : {
          "200" : {
            "description" : "Password was successfully changed",
            "schema" : {
              "type" : "object",
              "properties" : {
                "result" : {
                  "type" : "string",
                  "description" : "success"
                },
                "description" : {
                  "type" : "string",
                  "description" : "Password was successfully changed"
                }
              }
            }
          }
        }
      }
    }
  },
  "securityDefinitions" : {
    "HTTP_BASIC" : {
      "description" : "All GET methods are public, meaning that *you can read all the data*. Write operations require authentication and therefore are forbidden to the general public.",
      "type" : "basic"
    }
  },
  "definitions" : {
    "Error" : {
      "type" : "object",
      "description" : "This general error structure is used throughout this API.",
      "example" : "{\n  \"error_number\":  700,\n  \"description\": \"Incorrect login or password\",\n  \"result\": \"failed\"\n}"
    }
  }
}
