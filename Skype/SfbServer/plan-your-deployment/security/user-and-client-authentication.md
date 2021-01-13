---
title: Skype for Business Server のユーザーとクライアントの認証
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 信頼できるユーザーとは、資格情報が Skype for Business Server の信頼済みサーバーによって認証されているユーザーです。 このサーバーは、通常、Standard Edition サーバー、Enterprise Edition フロント エンド サーバー、またはディレクターです。 Skype for Business Server は、ユーザー資格情報の信頼できる単一のバック エンド リポジトリとして Active Directory ドメイン サービスに依存しています。
ms.openlocfilehash: bf0bde8478cd6c4e2eb068ffade7fba7fac14d56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832007"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Skype for Business Server のユーザー認証とクライアント認証
 
信頼できるユーザーとは、資格情報が Skype for Business Server の信頼済みサーバーによって認証されているユーザーです。 このサーバーは、通常、Standard Edition サーバー、Enterprise Edition フロント エンド サーバー、またはディレクターです。 Skype for Business Server は、ユーザー資格情報の信頼できる単一のバック エンド リポジトリとして Active Directory ドメイン サービスに依存しています。
  
認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。 Skype for Business Server は、ユーザーの状態と場所に応じて、次の認証プロトコルを使用します。
  
- **MIT Kerberos Version 5 セキュリティ プロトコル**: Active Directory の資格情報を持つ内部ユーザーに対して使用されます。Kerberos では、クライアントが Active Directory ドメイン サービスに接続できる状態であることが必要です。このため、Kerberos は企業のファイアウォールの外側にいるクライアントの認証には使用できません。
    
- **NTLM プロトコル**: Active Directory の資格情報を持ち、企業のファイアウォールの外側にあるエンドポイントから接続しているユーザーに対して使用されます。アクセス エッジ サービスによってログオン要求がディレクター (ある場合) またはフロントエンド サーバーに渡され、そこで認証が行われます。アクセス エッジ サービス自体では認証は行われません。
    
    > [!NOTE]
    > NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。 その結果、Skype for Business Server へのアクセスが内部または VPN または DirectAccess 接続経由で接続されているクライアントに制限される場合があります。 
  
- **ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。
    
Skype for Business Server 認証は、次の 2 つのフェーズで構成されます。
  
1. クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。
    
2. クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。
    
ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。
  
フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。
  
ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。
  
クライアント証明書は、ユーザーが Skype for Business Server によって認証される別の方法を提供します。 ユーザーは、ユーザー名とパスワードを指定する代わりに、暗号化チャレンジの解決に必要な証明書に対応する証明書とプライベート キーを持っています。 (この証明書には、ユーザーを識別するサブジェクト名またはサブジェクトの代替名が必要です。また、Skype for Business Server を実行しているサーバーによって信頼され、証明書の有効期間内に失効していないルート CA によって発行される必要があります)。認証を受け取る場合、ユーザーは暗証番号 (PIN) を入力する必要があります。 証明書は、ユーザー名とパスワードの入力が困難な電話、携帯電話、その他のデバイスで特に役立ちます。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>ASP .NET 4.5 による暗号化要件 

Skype for Business Server 2015 CU5 では、AES は ASP.NET 4.6 ではサポートされていません。このため、Skype 会議アプリの起動が失敗する可能性があります。 クライアントがマシン キー検証値として AES を使用している場合は、マシンキーの値を IIS の Skype 会議アプリ サイト レベルで SHA-1 または別のサポートされるアルゴリズムにリセットする必要があります。 必要に応じて、 [手順については、「IIS 8.0 ASP.NET Configuration Management」](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) を参照してください。
  
その他のサポートされる値は次のとおりです。
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  AES、3DES、および MD5 の値は、4 の場合と同様にASP.NETなくなりました。 [ASP.NET 4.5 pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) の暗号化の機能強化の詳細が示されています。
  
