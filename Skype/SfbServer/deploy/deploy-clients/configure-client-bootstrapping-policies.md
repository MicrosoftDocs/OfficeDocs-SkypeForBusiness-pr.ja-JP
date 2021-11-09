---
title: クライアント ブートストラップ ポリシーの構成
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: '概要: グループ ポリシーを管理する方法。'
ms.openlocfilehash: 073bd23219b3fa0a39ed06a94a5ef0586a740e6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831651"
---
# <a name="configure-client-bootstrapping-policies"></a>クライアント ブートストラップ ポリシーの構成
 
**概要:** グループ ポリシーを管理する方法。
  
グループ ポリシー管理コンソール (GPMC) とグループ ポリシー オブジェクト エディターは、グループ ポリシーの管理に使用するツールです。 Office グループ ポリシー管理テンプレートには、ドメイン内のグループ ポリシー オブジェクト用に構成する Skype for Business のレジストリ ベースのポリシー設定が含まれる lync16.admx (ADMX) と .adml (ADML) 管理用テンプレートが含まれます。 ADML ファイルは、ADMX ファイルの言語固有の補数です。 各 ADMX ファイルと ADML ファイルには、1 つのアプリケーションのポリシー設定Officeがあります。 Microsoft ダウンロード[センター Office 2016 管理用テンプレート ファイル (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)を無料でダウンロードできます。
  
クライアントSkype for Business、ユーザーが初めてサーバーにサインインする前に構成を検討する必要があるいくつかのクライアント ブートストラップ ポリシーがあります。 たとえば、サインインが完了するまでクライアントが使用する既定のサーバーとセキュリティ モードです。 グループ ポリシーを使用して、ユーザーがサインインし、サーバーからインバンド プロビジョニング設定の受信を開始する前に、ユーザーのコンピューター レジストリでこれらの設定を確立できます。 次の表に、グループ ポリシーで使用できるグループ ポリシー設定を示Skype for Business。
  
**グループ ポリシー 設定のSkype for Business**

|グループ ポリシー設定|説明|
|:-----|:-----|
|サーバーの指定 (ConfigurationMode)  <br/> | サインイン時Skype for Business使用するトランスポートとサーバーを識別する方法を指定します。 この設定では、次の値を指定します。 <br/>  ServerAddressExternal: 外部ファイアウォールの外部から接続するときにクライアントとフェデレーション連絡先によって使用されるサーバー名または IP アドレスを指定します。 <br/>  ServerAddressInternal: クライアントが組織のファイアウォール内から接続するときに使用するサーバー名または IP アドレスを指定します。 <br/>  トランスポート: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のいずれかを指定します。 <br/> |
|サポートされるその他のサーバーバージョン (ConfiguredServerCheckValues)  <br/> |既定でサポートされているサーバー バージョンに加えて、Skype for Business Server がログオンするセミコロンで区切られたサーバー バージョン名の一覧を指定します。  <br/> |
|サインインエラー ログの自動アップロードを無効にする (DisableAutomaticSendTracing)  <br/> |サインインエラー ログを自動的にアップロードして、Skype for Business Serverにアップロードします。 サインインが成功した場合、ログは自動的にアップロードされません。 このポリシーが構成されていない場合、次のことが発生します。  <br/> オンライン Skype for Businessの場合: サインインエラー ログは自動的にアップロードされます。 オンプレミスSkype for Businessの場合:アップロード前に確認ダイアログ ボックスがユーザーに表示されます。 この設定を無効にすると、サインイン ログは、オンプレミスユーザーとオンライン ユーザーの両方Skype for Business ServerにSkype for Business自動的にSkype for Businessされます。 この設定を有効にすると、サインイン ログは自動的にアップロードされません。  <br/> |
|SIP 接続の HTTP フォールバックを無効にする (DisableHttpConnect)  <br/> |TLS Skype for Business Server TCP が使用できない場合、HTTP を使用してサーバーに接続しようとするユーザーを防止します。 既定では、Skype for Businessは TLS または TCP を使用してサーバーへの接続を最初に試行し、どちらのトランスポートメソッドも成功しない場合、Skype for Business は HTTP を使用して接続を試行します。 このポリシーは、フォールバックの HTTP 接続試行を無効にするために使用します。  <br/> |
|ログオン資格情報を要求する (DisableNTCredentials)  <br/> |ユーザーは、SIP サーバーへのサインイン時にSkype for Business資格情報を自動的Windows使用するのではなく、ユーザーにログオン資格情報を提供する必要があります。  <br/> |
|サーバーのバージョン チェックを無効にする (DisableServerCheck)  <br/> |このポリシーを 1 に設定すると、サインインSkype for Businessサーバー名とバージョンを確認できません。 既定では、サインインSkype for Business前にこれらのチェックが実行されます。  <br/> |
|BITS を使用してアドレス帳サービス ファイルをダウンロードする (EnableBitsForGalDownload)  <br/> |バックグラウンド Skype for Business転送サービス (BITS) を使用してアドレス帳サービス ファイルをダウンロードできます。  <br/> |
|SIP セキュリティ モードの構成 (EnableSIPHighSecurityMode)  <br/> |インスタント Skype for Businessを安全に送受信できます。 このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。  <br/> このポリシー設定を構成しない場合は、Skype for Businessを使用できます。 ただし、TLS を使用しない場合や、サーバーがユーザーを認証する場合は、NTLM Skype for Business Kerberos 認証を使用する必要があります。  <br/> |
|グローバル アドレス帳ダウンロード初期遅延 (GalDownloadInitialDelay)  <br/> |グローバル アドレス一覧 (GAL) のダウンロードが行われる前の期間を指定します。 既定値は 60 分です。つまり、サーバーは GAL ファイルのダウンロードを 0 ~ 60 分のランダムな期間遅延します。  <br/> |
|ユーザーがファイルを実行Skype for Businessする (PreventRun)  <br/> |ユーザーがファイルを実行Skype for Business。 このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。  <br/> |
|ユーザー パスワードの保存を許可する (SavePassword)  <br/> |パスワードSkype for Businessを保存できます。  <br/> |
|SIP 圧縮モードの構成 (SipCompression)  <br/> |SIP 圧縮を有効にする時間を指定します。 既定では、SIP 圧縮はアダプターの速度に基づいて有効になっています。 このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。  <br/> |
|信頼されたドメイン リスト (TrustModelData)  <br/> |顧客 SIP ドメインのプレフィックスと一致しない信頼できるドメインを一覧表示します。  <br/> |
   
サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。
  
**グループ ポリシーの優先順位**

|**Precedence**|**設定の場所と方法**|
|:-----|:-----|
|1  <br/> |Skype for Business Serverインバンド プロビジョニング  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |[オプション] ダイアログ ボックス (Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>管理用テンプレート ファイルを使用してグループ Skype for Business設定を定義するには

1. すべての言語に依存しない ADMX ファイルを含むルート レベルのフォルダーを作成します。 たとえば、次の場所にあるドメイン コントローラーの中央ストアのルート フォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > この手順では、ドメイン内の複数のコンピューターを管理する必要があります。 この場合、テンプレートはプライマリ ドメイン コントローラーの Sysvol フォルダーの中央ストアに格納します。 これはドメインの管理用テンプレートのためのレプリケートされた集中格納場所となります。 
  
2. 使用する言語ごとにサブフォルダーを作成します。 これらのサブフォルダーには、言語固有の ADML リソース ファイルが含まれる。 たとえば、次の場所に米国英語 (EN-US) のサブフォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

