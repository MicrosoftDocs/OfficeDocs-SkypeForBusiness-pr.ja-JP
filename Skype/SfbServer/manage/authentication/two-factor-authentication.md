---
title: Skype for Business Server で 2 要素認証を管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '概要: Skype for Business Server で 2 要素認証を管理します。'
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806544"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Skype for Business Server で 2 要素認証を管理する
 
**概要:** Skype for Business Server で 2 要素認証を管理します。
  
2 要素認証では、ユーザー名/パスワードの組み合わせとトークンまたは証明書の 2 種類の認証または識別をユーザーに提供する必要が生じ、セキュリティが強化されます。 これは、"ユーザーが持っているもの、知っているもの" とも呼ばれる。 
  
証明書を使用した 2 要素認証の一般的な例として、スマート カードの使用があります。 スマート カードには、ユーザー アカウントに関連付けられた証明書が含まれているので、サーバーに保存されているユーザーおよび証明書の情報に対して検証できます。 ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーは資格情報を検証し、ユーザーを認証します。
  
2 要素認証をサポートする Skype for Business Server 環境を構成する場合は、次の点を考慮してください。
  
## <a name="client-support"></a>クライアント サポート

Lync Server 2013 の累積的な更新プログラム: 2013 年 7 月のデスクトップ クライアントと Skype for Business クライアントは、現在 2 要素認証をサポートしている唯一のクライアントです。
  
## <a name="topology-requirements"></a>トポロジ要件

お客様は、エッジ、ディレクター、およびユーザー プールを備える専用の Skype for Business Server を使用して、2 要素認証を展開強く推奨します。 ユーザーに対してパッシブ認証を有効にするには、次のような他の役割とサービスに対して他の認証方法を無効にする必要があります。
  
|**構成の種類**|**サービスの種類**|**サーバーの役割**|**無効にする認証の種類**|
|:-----|:-----|:-----|:-----|
|(Web) サービス  <br/> |WebServer  <br/> |ディレクター  <br/> |Kerberos、NTLM、および証明書  <br/> |
|(Web) サービス  <br/> |WebServer  <br/> |フロントエンド  <br/> |Kerberos、NTLM、および証明書  <br/> |
|プロキシ  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos および NTLM  <br/> |
|プロキシ  <br/> |レジストラー  <br/> |フロントエンド  <br/> |Kerberos および NTLM  <br/> |
   
これらの認証の種類がサービス レベルで無効になっていない限り、展開内で 2 要素認証が有効になると、他のすべてのバージョンのクライアントは正常にサインインできません。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business サービスの検出

内部クライアントや外部クライアントが Skype for Business サービスを検出するために使用する DNS レコードは、2 要素認証が有効になっていない Skype for Business サーバーに解決するように構成する必要があります。 この構成では、2 要素認証が有効になっていない Skype for Business プールのユーザーは認証のために PIN を入力する必要はありません。一方、2 要素認証が有効になっている Skype for Business プールのユーザーは、認証のために PIN を入力する必要があります。
  
## <a name="exchange-authentication"></a>Exchange 認証

Microsoft Exchange の 2 要素認証を展開しているお客様は、クライアント内の特定の機能が使用できないことに気が付く場合があります。 Skype for Business クライアントは Exchange 統合に依存する機能に対して 2 要素認証をサポートしていないので、これは現在設計されています。
  
## <a name="contacts"></a>連絡先

統合連絡先ストア機能を利用するように構成されている Skype for Business ユーザーは、2 要素認証でサインインした後に連絡先を利用できなくなりました。
  
2 要素認証を有効にする前に **、Invoke-CsUcsRollback** コマンドレットを使用して、既存のユーザー連絡先を統合連絡先ストアから削除し、それらを Skype for Business Server に保存する必要があります。
  
## <a name="skill-search"></a>スキル検索

Skype for Business 環境でスキル検索機能を構成したお客様は、Skype for Business で 2 要素認証が有効になっている場合、この機能は機能しません。 現在、Microsoft SharePoint は 2 要素認証をサポートしていないので、これは設計上の問題です。
  
## <a name="credentials"></a>資格情報

保存された Skype for Business 資格情報は、2 要素認証を使用するように構成されているユーザーに影響を与える可能性がある展開に関する考慮事項が多数ある。
  
### <a name="deleting-saved-credentials"></a>保存された資格情報の削除

ユーザーは、2 要素認証を使用して初めてサインインする前に、Skype for Business クライアントの [サインイン情報の削除] オプションを使用し、SIP プロファイル フォルダーを %localappdata%\Microsoft\Office\15.0\Skype for Business から削除する必要があります。 
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos または NTLM 認証方式では、ユーザーの Windows 資格情報が認証に自動的に使用されます。 認証に対して Kerberos または NTLM が有効になっている一般的な Skype for Business Server 展開では、ユーザーはサインインの度に資格情報を入力する必要がなされません。
  
PIN の入力を求めるメッセージが表示される前に、ユーザーに資格情報の入力を求めるメッセージが意図せずに表示された場合 **、DisableNTCredentials** レジストリ キーがクライアント コンピューター上で意図せず構成されている可能性があります (場合によっては、グループ ポリシーによって)。
  
資格情報の追加のプロンプトが表示されるのを防ぐには、ローカル ワークステーションで次のレジストリ エントリを作成するか、Skype for Business 管理テンプレートを使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

ユーザーが初めて Skype for Business にサインインすると、ユーザーは自分のパスワードを保存するように求められます。 このオプションを選択すると、ユーザーのクライアント証明書を個人用証明書ストアに格納し、ユーザーの Windows 資格情報をローカル コンピューターの資格情報マネージャーに格納できます。
  
**2 要素認証を** サポートするように Skype for Business が構成されている場合は、SavePassword レジストリ設定を無効にする必要があります。 ユーザーがパスワードを保存しなくするには、ローカル ワークステーションで次のレジストリ エントリを変更するか、Skype for Business 管理テンプレートを使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 トークンの再生

AD FS 2.0 には、同じトークンを使用した複数のトークン要求を検出して破棄できる、トークン再生検出と呼ばれる機能が用意されています。 この機能を有効にすると、トークン再生検出は、同じトークンが 2 回使用されたことがないことを確認することで、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方の認証要求の整合性を保護します。
  
キオスクを使用する場合など、セキュリティが非常に高い懸念事項である場合は、この機能を有効にする必要があります。 トークン再生検出の詳細については [、「Secure Planning and Deployment for Secure Planning and Deployment of AD FS 2.0」](https://go.microsoft.com/fwlink/p/?LinkId=309215)を参照してください。
  
## <a name="external-user-access"></a>外部ユーザー アクセス

外部ネットワークからの Skype for Business 2 要素認証をサポートするために ADFS プロキシまたはリバース プロキシを構成する方法については、以下のトピックでは説明されていません。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server で 2 要素認証を構成する](configure-two-factor.md)
  
