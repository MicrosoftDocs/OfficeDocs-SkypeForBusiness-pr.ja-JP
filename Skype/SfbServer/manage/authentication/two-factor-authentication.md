---
title: Skype のビジネス サーバーの 2 要素による認証を管理します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '概要: は、Skype のビジネス サーバーの 2 要素による認証を管理します。'
ms.openlocfilehash: ce6d43b8ace741a754cb4406235534fd83e414b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222878"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Skype のビジネス サーバーの 2 要素による認証を管理します。
 
**の概要:** Skype のビジネス サーバーの 2 要素による認証を管理します。
  
2 要素認証では、ユーザーが 2 つの形式の認証情報または識別情報、つまりユーザー名/パスワードの組み合わせと、トークンまたは証明書を提示する必要があるため、セキュリティが強化されます。 これとも呼ばれるものがある場合、知っていること。 
  
証明書を使用した 2 要素認証の一般的な例として、スマート カードの使用があります。スマート カードにはユーザー アカウントに関連付けられている証明書が格納されていて、サーバーに格納されているユーザー情報と証明書情報に対する検証を行うことができます。ユーザー情報 (ユーザー名とパスワード) と提供された証明書を比較することで、サーバーでは資格情報を検証し、ユーザーを認証します。
  
2 要素認証をサポートするには、ビジネスのサーバー環境に Skype を設定するときは、次の項目を検討してください。
  
## <a name="client-support"></a>クライアントのサポート

Lync Server 2013 の累積的な更新: 2013年 7 月デスクトップ クライアントおよびビジネス クライアント用の Skype は、2 要素認証がサポートされているクライアントのみです。
  
## <a name="topology-requirements"></a>トポロジ要件

お客様は、ビジネスのサーバーのエッジ、ディレクター、およびユーザーのプールと専用の Skype を使用して 2 段階認証を導入するよう強くお勧めします。 ユーザーに対してパッシブ認証を有効にするには、次に示すように、他の役割およびサービスに対してその他の認証方法を無効にする必要があります。
  
|**構成の種類**|**サービスの種類**|**サーバーの役割**|**無効にする認証の種類**|
|:-----|:-----|:-----|:-----|
|Web サービス  <br/> |WebServer  <br/> |ディレクター  <br/> |Kerberos、NTLM、証明書  <br/> |
|Web サービス  <br/> |WebServer  <br/> |フロントエンド  <br/> |Kerberos、NTLM、証明書  <br/> |
|プロキシ  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos および NTLM  <br/> |
|プロキシ  <br/> |レジストラー  <br/> |フロントエンド  <br/> |Kerberos および NTLM  <br/> |
   
これらの認証の種類がサービス レベルで無効になっていない限り、2 要素認証が展開内で有効になっても、他のすべてのバージョンのクライアントでは正常にサインインできません。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business サービスの検出

Skype の二要素認証を有効になっていないビジネス サーバーを解決するのには、ビジネス ・ サービスの Skype を検出する内部および外部のクライアントによって使用される DNS レコードを構成してください。 この構成では、2 要素認証は有効でないビジネス ・ プールの Skype ユーザー必要はありませんビジネス ・ プール 2 要素認証は有効になっている Skype からユーザー間を認証する PIN を入力するのには認証する PIN を入力する必要です。
  
## <a name="exchange-authentication"></a>Exchange 認証

Microsoft Exchange 向けの二要素認証を導入しているお客様は、クライアントの特定の機能が使用できないことにあります。 これは、現在仕様では、ビジネス クライアント用の Skype では Exchange の統合に依存している機能の二要素認証がサポートされていません。
  
## <a name="contacts"></a>連絡先

連絡先が不要になった使用可能な二要素認証を使用してサインインした後に、統合連絡先ストアの機能を活用するように構成されているビジネス ユーザーの Skype が見つかります。
  
統合連絡先ストアから既存のユーザーの連絡先を削除し、保存 Skype のビジネス サーバーの 2 要素認証を有効にする前に、**呼び出し CsUcsRollback**コマンドレットを使用する必要があります。
  
## <a name="skill-search"></a>スキル検索

二要素認証のビジネス用の Skype が有効になっているときに、この機能が動作しないことには、お客様のビジネス環境に、Skype でスキル検索機能を構成しているが見つかります。 現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。
  
## <a name="credentials"></a>資格情報

2 要素認証を使用するように構成されているユーザーに影響を与えるビジネスの資格情報を保存されている Skype に関連する展開の考慮事項の多くがあります。
  
### <a name="deleting-saved-credentials"></a>保存された資格情報の削除

ユーザーが、Skype で**自分のサインイン情報を削除**する] オプションを使用して、ビジネスのクライアントと、SIP プロファイルからフォルダーを削除 %localappdata%\Microsoft\Office\15.0\Skype ビジネスの 2 つの要素を使用して最初にサインインする前にする必要があります。認証します。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos または NTLM の認証方法とユーザーの Windows 資格情報を自動的に認証に使用します。 ビジネス サーバー配置では、Kerberos または NTLM 認証が有効の典型的な Skype、ユーザー必要はありませんにサインインするたびに資格情報を入力します。
  
PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。
  
資格情報の追加のプロンプトを避けるためには、ローカル ワークステーションで次のレジストリ エントリを作成または管理用テンプレートをビジネス用の Skype を使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

最初に、Skype をビジネスのためにユーザーがサインインすると、ときに、自分のパスワードを保存するのには求められます。 選択した場合、このオプションでは、ユーザーのクライアントの証明書を個人証明書ストアとローカル コンピューターの資格情報マネージャーに格納するユーザーの Windows の資格情報に格納します。
  
2 要素認証をサポートするためにビジネス用の Skype が構成されている場合は、 **SavePassword**レジストリ設定を無効にする必要があります。 ユーザーが自分のパスワードを保存することを防ぐ、ローカル ワークステーションで次のレジストリ エントリを変更または管理用テンプレートをビジネス用の Skype を使用して、グループ ポリシーを使用して特定のプールのすべてのユーザーに適用します。
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 のトークンのリプレイ

AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。
  
キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。 トークンのリプレイ検出の詳細については、 [AD FS 2.0 のセキュリティ保護の計画および展開のベスト プラクティス](https://go.microsoft.com/fwlink/p/?LinkId=309215)を参照してください。
  
## <a name="external-user-access"></a>外部ユーザー アクセス

Skype を外部ネットワークからビジネスの 2 要素認証をサポートするには、ad FS プロキシまたはリバース プロキシを構成する」のトピックでは説明しません。
  
## <a name="see-also"></a>関連項目

[Skype のビジネス サーバーの 2 要素認証を構成します。](configure-two-factor.md)
  
