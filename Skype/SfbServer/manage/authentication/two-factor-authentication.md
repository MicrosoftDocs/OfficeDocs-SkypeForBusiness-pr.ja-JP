---
title: 2 要素認証を管理Skype for Business Server
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
description: '概要: 2 要素認証を管理Skype for Business Server。'
ms.openlocfilehash: d73f088798938da6f5a87a8d21fa2922188f3bdc35e589dcda32b3f62747f0d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297303"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>2 要素認証を管理Skype for Business Server
 
**概要:** 2 要素認証を管理するには、Skype for Business Server。
  
2 要素認証では、ユーザーに 2 つの形式の認証または ID、ユーザー名/パスワードの組み合わせとトークンまたは証明書を提供する必要が生じ、セキュリティが強化されます。 これは「持っているもの、知っているもの」とも呼ばれる。 
  
証明書を使用した 2 要素認証の一般的な例は、スマート カードの使用です。 スマート カードには、ユーザー アカウントに関連付けられた証明書が含まれているので、サーバーに保存されているユーザーと証明書の情報に対して検証できます。 ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーは資格情報を検証し、ユーザーを認証します。
  
2 要素認証をサポートするためにSkype for Business Server環境を構成する場合は、次のテーマを検討してください。
  
## <a name="client-support"></a>クライアント サポート

Lync Server 2013 の累積的な更新プログラム: 2013 年 7 月のデスクトップ クライアントと Skype for Business クライアントは、現在 2 要素認証をサポートしている唯一のクライアントです。
  
## <a name="topology-requirements"></a>トポロジ要件

お客様は、エッジ、ディレクター、およびユーザー プールを使用して専用のSkype for Business Serverを使用して 2 要素認証を展開してください。 ユーザーのパッシブ認証を有効にするには、次のような他の役割とサービスに対して他の認証方法を無効にする必要があります。
  
|**構成の種類**|**サービスの種類**|**サーバーの役割**|**無効にする認証の種類**|
|:-----|:-----|:-----|:-----|
|(Web) サービス  <br/> |WebServer  <br/> |ディレクター  <br/> |Kerberos、NTLM、および証明書  <br/> |
|(Web) サービス  <br/> |WebServer  <br/> |フロントエンド  <br/> |Kerberos、NTLM、および証明書  <br/> |
|プロキシ  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos と NTLM  <br/> |
|プロキシ  <br/> |レジストラー  <br/> |フロントエンド  <br/> |Kerberos と NTLM  <br/> |
   
これらの認証の種類がサービス レベルで無効になっていない限り、展開内で 2 要素認証が有効になると、他のすべてのバージョンのクライアントは正常にサインインできません。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Businessサービスの検出

Skype for Business サービスを検出するために内部および/または外部クライアントが使用する DNS レコードは、2 要素認証が有効になっていない Skype for Business サーバーに解決するように構成する必要があります。 この構成では、2 要素認証が有効になっていない Skype for Business プールのユーザーは認証に PIN を入力する必要はありません。認証には 2 要素認証が有効になっている Skype for Business プールのユーザーが PIN を入力する必要があります。
  
## <a name="exchange-authentication"></a>Exchange認証

Microsoft クライアントに 2 要素認証を展開したExchange、クライアント内の特定の機能が使用できないことがあります。 現在、この機能は、Skype for Business統合に依存する機能に対する 2 要素認証をサポートしていないので、設計Exchangeです。
  
## <a name="contacts"></a>連絡先

Skype for Business統合連絡先ストア機能を利用するように構成されているユーザーは、2 要素認証でサインインした後、連絡先が使用できなくなったと感じます。
  
**Invoke-CsUcsRollback** コマンドレットを使用して、2 要素認証を有効にする前に、既存のユーザー連絡先を統合連絡先ストアから削除し、Skype for Business Server に保存する必要があります。
  
## <a name="skill-search"></a>スキル検索

2 要素認証が有効になっている場合、Skype for Business環境でスキル検索機能を構成したSkype for Business機能が機能しない場合があります。 これは設計上、Microsoft SharePointは現在 2 要素認証をサポートしていないのでです。
  
## <a name="credentials"></a>資格情報

2 要素認証を使用するように構成されているSkype for Businessに影響する可能性がある、保存された資格情報に関する展開に関する考慮事項が多数ある。
  
### <a name="deleting-saved-credentials"></a>保存された資格情報の削除

ユーザーは、Skype for Businessクライアントの [自分のサインイン情報を削除する] オプションを使用し、2 要素認証を使用して初めてサインインする前に、%localappdata%\Microsoft\Office\15.0\Skype for Business から SIP プロファイル フォルダーを削除する必要があります。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos または NTLM 認証方法では、ユーザーの資格情報Windows認証に自動的に使用されます。 Kerberos または NTLM Skype for Business Server認証が有効になっている一般的な展開では、ユーザーがサインインする度に資格情報を入力する必要があります。
  
PIN の入力を求めるメッセージが表示される前に、ユーザーが意図せずに資格情報を求めるメッセージが表示された場合は **、DisableNTCredentials** レジストリ キーが、クライアント コンピューター上で意図せずに構成されている可能性があります 。おそらくグループ ポリシーを使用します。
  
資格情報の追加のプロンプトが表示されるのを防ぐには、ローカル ワークステーションに次のレジストリ エントリを作成するか、Skype for Business 管理テンプレートを使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

ユーザーが初めてSkype for Businessにサインインすると、パスワードの保存を求めるメッセージが表示されます。 このオプションを選択すると、ユーザーのクライアント証明書を個人用証明書ストアに保存し、ユーザーの Windows 資格情報をローカル コンピューターの Credential Manager に保存できます。
  
**2 要素認証を** サポートするように構成されている場合Skype for Business SavePassword レジストリ設定を無効にする必要があります。 ユーザーがパスワードを保存しなくするには、ローカル ワークステーションで次のレジストリ エントリを変更するか、Skype for Business 管理テンプレートを使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 トークン再生

AD FS 2.0 には、同じトークンを使用する複数のトークン要求を検出してから破棄できる、トークン再生検出と呼ばれる機能が用意されています。 この機能を有効にすると、トークン再生検出によって、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方で、同じトークンが 2 回以上使用されないよう、認証要求の整合性が保護されます。
  
この機能は、キオスクの使用など、セキュリティが非常に懸念される状況で有効にする必要があります。 トークン再生の検出の詳細については、「ベスト プラクティス for [Secure Planning and Deployment of AD FS 2.0」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10))。
  
## <a name="external-user-access"></a>外部ユーザー アクセス

外部ネットワークからの 2 要素認証をサポートSkype for Business ADFS プロキシまたはリバース プロキシの構成については、以下のトピックでは説明されていません。
  
## <a name="see-also"></a>関連項目

[2 要素認証を構成Skype for Business Server](configure-two-factor.md)
