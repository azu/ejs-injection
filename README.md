# ejs is not for user defined template

[EJS](https://ejs.co/) is not safe for user defined template.
You shoud not use ejs as a user-defined template.

- [ejs/SECURITY.md at main · mde/ejs](https://github.com/mde/ejs/blob/main/SECURITY.md)

Payload:

```ejs
<%= console.log(process.env); %>
```

Run:

```ejs
$ ejs ./template_file.ejs-o ./output.html

{
  ...Your environment variables
}
```

ejs allow to run any JavaScript code in template by design.

If used incorrectly, It will cause RCE(Remote Code Execution) vulnerbility.
It is not ejs problem, It is your application problem.

## references

- [クライアントサイドからサーバサイドまで破壊するテンプレートエンジンを利用した攻撃と対策](https://azu.github.io/slide/2019/template-engine/template-engine-security.html)
