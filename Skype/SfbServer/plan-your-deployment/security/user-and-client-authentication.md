---
title: Skype for Business Server のユーザーとクライアントの認証
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 信頼されたユーザーとは、資格情報が Skype for Business Server の信頼されたサーバーによって認証されたユーザーのことです。 通常、このサーバーは Standard Edition server、Enterprise Edition のフロントエンドサーバー、またはディレクターです。 Skype for Business Server は、ユーザー資格情報の単一の信頼できるバックエンドリポジトリとして Active Directory ドメインサービスに依存します。
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815585"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Skype for Business Server のユーザーとクライアントの認証
 
信頼されたユーザーとは、資格情報が Skype for Business Server の信頼されたサーバーによって認証されたユーザーのことです。 通常、このサーバーは Standard Edition server、Enterprise Edition のフロントエンドサーバー、またはディレクターです。 Skype for Business Server は、ユーザー資格情報の単一の信頼できるバックエンドリポジトリとして Active Directory ドメインサービスに依存します。
  
認証では、ユーザーの資格情報が信頼されたサーバーに渡されます。 Skype for Business Server では、ユーザーの状態と場所に応じて、次の認証プロトコルが使用されます。
  
- Active Directory 資格情報を持つ内部ユーザー用の**MIT Kerberos バージョン5セキュリティプロトコル**。 Kerberos には Active Directory ドメインサービスへのクライアント接続が必要です。このため、会社のファイアウォール以外のクライアントを認証するために使用することはできません。
    
- 企業ファイアウォール外のエンドポイントから接続している Active Directory 資格情報を持つユーザーの**NTLM プロトコル**。 アクセスエッジサービスは、ログイン要求をディレクター (存在する場合) または認証用のフロントエンドサーバーに渡します。 アクセスエッジサービス自体では、認証は実行されません。
    
    > [!NOTE]
    > NTLM プロトコルは Kerberos ほど攻撃に対して強くないので、NTLM の使用を最小限にしている組織もあります。 その結果、Skype for Business Server へのアクセスが、VPN または DirectAccess 接続経由で接続されている内部またはクライアントに制限されている可能性があります。 
  
- **ダイジェスト プロトコル**: いわゆる匿名ユーザーに対して使用されます。匿名ユーザーは、有効な Active Directory の資格情報は持たないが、社内会議に招待され、有効な会議キーを持つ外部ユーザーです。ダイジェスト認証は、他のクライアント操作には使用されません。
    
Skype for Business Server 認証は、次の2つのフェーズで構成されます。
  
1. クライアントとサーバーの間に、セキュリティ アソシエーションが確立されます。
    
2. クライアントとサーバーは、既存のセキュリティ アソシエーションを使用して、送信するメッセージに署名し、受信するメッセージを検証します。サーバーで認証が有効になっている場合、クライアントからの認証されていないメッセージは受信されません。
    
ユーザーの信用情報は、ユーザー ID 自体ではなく、ユーザーから送信される各メッセージに添付されます。サーバーは、各メッセージについて、送信元ユーザーの資格情報が有効であるかどうか確認します。ユーザーの資格情報が有効な場合、そのメッセージを受け取る最初のサーバーだけでなく、信頼済みサーバー クラウドに属する他のすべてのサーバーで、そのメッセージが受信できるようになります。
  
フェデレーション パートナーが発行した有効な資格情報を持つユーザーは信頼されますが、これらのユーザーに対しては、内部ユーザーに与えられる権限のうち一部の使用を、必要に応じて制限できます。
  
ICE プロトコルおよび TURN プロトコルでも、IETF TURN RFC に記載されているとおり、ダイジェスト認証が使用されます。
  
クライアント証明書は、ユーザーが Skype for Business Server による認証を行うための代替手段を提供します。 ユーザー名とパスワードを提供する代わりに、ユーザーは証明書と、暗号化認証の解決に必要な証明書に対応する秘密キーを持ちます。 (この証明書には、ユーザーを識別するサブジェクト名またはサブジェクトの別名が必要です。また、Skype for Business Server を実行しているサーバーによって信頼され、証明書の有効期間内であり、失効していないルート CA によって発行されている必要があります)。認証するには、個人識別番号 (PIN) を入力する必要があります。 証明書は、ユーザー名とパスワードを入力することが難しい電話、携帯電話、その他のデバイスで特に便利です。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>ASP .NET 4.5 に基づく暗号化要件 

Skype for Business Server 2015 CU5 以降の場合、AES は ASP.NET 4.6 ではサポートされていないため、Skype 会議アプリの起動が失敗することがあります。 クライアントがマシンキーの検証値として AES を使用している場合は、コンピューターのキー値を SHA-1 にリセットするか、IIS の Skype 会議アプリのサイトレベルでサポートされている別のアルゴリズムに再設定する必要があります。 必要に応じて、「 [IIS 8.0 ASP.NET 構成管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)の手順」を参照してください。
  
その他に次の値がサポートされます。
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  ASP.NET 4 ではサポートされていた AES、3DES、MD5 の値は使用できなくなりました。 [ASP.NET 4.5 での暗号化の改善](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)の詳細については、こちらをご覧ください。
  
