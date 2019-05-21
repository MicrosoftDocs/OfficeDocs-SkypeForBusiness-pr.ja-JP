---
title: Skype for Business Server で2要素認証を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '概要: Skype for Business Server で2要素認証を管理します。'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297562"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Skype for Business Server で2要素認証を管理する
 
**概要:** Skype for Business Server で2要素認証を管理する。
  
2 要素認証では、ユーザーが 2 つの形式の認証情報または識別情報、つまりユーザー名/パスワードの組み合わせと、トークンまたは証明書を提示する必要があるため、セキュリティが強化されます。 これは、「持っていること、知っていること」とも呼ばれます。 
  
証明書を使用した 2 要素認証の一般的な例として、スマート カードの使用があります。スマート カードにはユーザー アカウントに関連付けられている証明書が格納されていて、サーバーに格納されているユーザー情報と証明書情報に対する検証を行うことができます。ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーでは資格情報を検証し、ユーザーを認証します。
  
Skype for Business Server 環境を構成して、2段階認証をサポートする場合は、次の点を考慮してください。
  
## <a name="client-support"></a>クライアントのサポート

Lync Server 2013 の累積的な更新: 2013 年7月のデスクトップクライアントと Skype for Business クライアントは、現在2要素認証をサポートしている唯一のクライアントです。
  
## <a name="topology-requirements"></a>トポロジ要件

お客様は、エッジ、監督、ユーザープールと共に、専用の Skype for Business Server を使用して2要素認証を展開することを強くお勧めします。 ユーザーに対してパッシブ認証を有効にするには、次に示すように、他の役割およびサービスに対してその他の認証方法を無効にする必要があります。
  
|**構成の種類**|**サービスの種類**|**サーバーの役割**|**無効にする認証の種類**|
|:-----|:-----|:-----|:-----|
|Web サービス  <br/> |WebServer  <br/> |ディレクター  <br/> |Kerberos、NTLM、証明書  <br/> |
|Web サービス  <br/> |WebServer  <br/> |フロントエンド  <br/> |Kerberos、NTLM、証明書  <br/> |
|プロキシ  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos および NTLM  <br/> |
|プロキシ  <br/> |レジストラー  <br/> |フロントエンド  <br/> |Kerberos および NTLM  <br/> |
   
これらの認証の種類がサービス レベルで無効になっていない限り、2 要素認証が展開内で有効になっても、他のすべてのバージョンのクライアントでは正常にサインインできません。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business サービスの検出

Skype for business サービスを検出するために、内部または外部のクライアントによって使用される DNS レコードは、2要素認証が有効になっていない Skype for Business サーバーに解決するように構成する必要があります。 この構成では、2要素認証が有効になっていない Skype for Business プールのユーザーは、認証のために PIN を入力する必要がなく、2要素認証が有効になっている Skype for Business プールのユーザーは実行されません。認証のために PIN を入力する必要があります。
  
## <a name="exchange-authentication"></a>Exchange 認証

Microsoft Exchange の2要素認証を導入しているお客様は、クライアントの一部の機能が利用できない可能性があります。 現時点では、Skype for Business クライアントは Exchange 統合に依存する機能に対して2要素認証をサポートしていないため、これは現在設計になっています。
  
## <a name="contacts"></a>連絡先

ユニファイド連絡先ストア機能を利用するように構成されている Skype for Business ユーザーは、2要素認証を使用してサインインした後、連絡先を使用できなくなります。
  
2要素認証を有効にする前に、 **CsUcsRollback**コマンドレットを使用して、統合された連絡先ストアから既存のユーザーの連絡先を削除し、それらを Skype For business Server に保存する必要があります。
  
## <a name="skill-search"></a>スキル検索

Skype for Business 環境でスキル検索機能を構成している場合は、Skype for Business が2要素認証を有効にしているときに、この機能が機能しないことがわかります。 現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。
  
## <a name="credentials"></a>資格情報

2要素認証を使用するように構成されているユーザーに影響を与える可能性のある、Skype for Business の資格情報を保存することについて、いくつかの展開の考慮事項があります。
  
### <a name="deleting-saved-credentials"></a>保存された資格情報の削除

ユーザーは、Skype for Business クライアントで **[サインイン情報の削除**] オプションを使用し、2つの要素を使用して初めてサインインする前に、%Localappdata%\Microsoft\Office\15.0\Skype for BUSINESS から SIP プロファイルフォルダーを削除する必要があります。認証.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos 認証方法または NTLM 認証方法を使用すると、ユーザーの Windows 資格情報が認証に自動的に使用されます。 Skype for Business Server の一般的な展開では、認証に Kerberos または NTLM が有効になっているため、ユーザーはサインインするたびに資格情報を入力する必要はありません。
  
PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。
  
追加の資格情報の入力を求めるメッセージが表示されないようにするには、ローカルワークステーションで次のレジストリエントリを作成するか、グループポリシーを使って特定のプールのすべてのユーザーに適用する Skype for Business 管理用テンプレートを使用します。
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

ユーザーが初めて Skype for Business にサインインしたときに、ユーザーにパスワードの保存を促すメッセージが表示されます。 このオプションを選択すると、ユーザーのクライアント証明書が個人証明書ストアに保存され、ユーザーの Windows 資格情報がローカルコンピューターの資格情報マネージャーに格納されるようになります。
  
Skype for Business が2要素認証をサポートするように構成されている場合は、 **Savepassword**レジストリ設定を無効にする必要があります。 ユーザーがパスワードを保存できないようにするには、ローカルワークステーション上の次のレジストリエントリを変更するか、グループポリシーを使って特定のプールのすべてのユーザーに適用する Skype for Business 管理用テンプレートを使用します。
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 のトークンのリプレイ

AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。
  
キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。 トークンの再生検出の詳細については、「 [AD FS 2.0 のセキュリティで保護された計画と展開のためのベストプラクティス](https://go.microsoft.com/fwlink/p/?LinkId=309215)」を参照してください。
  
## <a name="external-user-access"></a>外部ユーザー アクセス

外部ネットワークからの Skype for Business の2要素認証をサポートするために ADFS プロキシまたはリバースプロキシを構成する方法については、以下のトピックを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server で2要素認証を構成する](configure-two-factor.md)
  
