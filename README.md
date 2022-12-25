# RustDeskApi
Simple Api Server implementation for [rustdesk](https://github.com/rustdesk/rustdesk).

#### Features
* Autenticate user
* Store user's address book

#### Platfrom
.Net 7.0, can run on Windows, Linux and MacOS

#### Description
- The appsettings.json file is used to store user's login/password. You can add additional users in the Users section:

```json
"Users": [
    {
        "Login": "user",
        "Password": "123456"
    }
]
```

- The user's address book uses embedded LiteDB database with an automatically generated api.db file.

#### Install as daemon on Linux

- Install [.Net 7.0 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/7.0)
- Run `dotnet publish -c Release -f "net7.0" -o ./publish ./RustDeskApi.csproj`
- Copy publish directory to the target machine, default path is `/var/rustdeskapi`. If you uses another directory change path in `rustdeskapi.service` file.
- Run `sudo install.sh`

Bash script will install and configure rustdeskapi.service in systemd.

#### License

The software released under the terms of the MIT license.