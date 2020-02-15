---
title: クライアントブートストラップポリシーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: '概要: グループポリシーを管理する方法について説明します。'
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029058"
---
# <a name="configure-client-bootstrapping-policies"></a>クライアントブートストラップポリシーを構成する
 
**概要:** グループポリシーを管理する方法。
  
グループポリシー管理コンソール (GPMC) とグループポリシーオブジェクトエディタは、グループポリシーの管理に使用するツールです。 Office グループポリシー管理用テンプレートに含まれているのは、ドメイン内のグループポリシーオブジェクトに対して構成されている Skype for Business のレジストリベースのポリシー設定を含む lync16 (ADMX) および adml (ADML) 管理用テンプレートです。 ADML ファイルは、ADMX ファイルに対して言語固有の補完を備えています。 各 ADMX および ADML ファイルには、1つの Office アプリケーションのポリシー設定が含まれています。 [Office 2016 管理用テンプレートファイル (ADMX/ADML) は](https://www.microsoft.com/download/details.aspx?id=49030)、Microsoft ダウンロードセンターから無料でダウンロードできます。
  
Skype for Business クライアントの場合、ユーザーが初めてサーバーにサインインする前に構成を考慮する必要があるクライアントブートストラップポリシーがいくつかあります。 たとえば、サインインが完了するまでクライアントが使用する既定のサーバーおよびセキュリティモード。 グループポリシーを使用して、ユーザーのコンピューターのレジストリでこれらの設定を行い、サインインしてから、サーバーからインバンドプロビジョニング設定を受信することができます。 次の表に、Skype for Business で使用できるグループポリシー設定を示します。
  
**Skype for Business のグループポリシー設定**

|グループ ポリシー設定|説明|
|:-----|:-----|
|サーバーを指定する (ConfigurationMode)  <br/> | Skype for Business がサインイン時に使用するトランスポートおよびサーバーを識別する方法を指定します。 この設定では、以下のことを指定します。 <br/>  ServerAddressExternal: 外部ファイアウォールの外側から接続する場合に、クライアントとフェデレーション連絡先が使用するサーバー名または IP アドレスを指定します。 <br/>  ServerAddressInternal: クライアントが組織のファイアウォールの内側から接続するときに使用されるサーバー名または IP アドレスを指定します。 <br/>  Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のどちらかを指定します。 <br/> |
|サポートされているその他のサーバーバージョン (ConfiguredServerCheckValues)  <br/> |既定でサポートされているサーバーのバージョンに加えて、Skype for Business Server がログオンするサーバーのバージョン名の一覧をセミコロンで区切って指定します。  <br/> |
|サインイン失敗ログの自動アップロードを無効にする (Disableautomatic Sendtracing)  <br/> |サインインエラーログを分析のために Skype for Business Server に自動的にアップロードします。 サインインに成功した場合、ログは自動的にアップロードされません。 このポリシーが構成されていない場合、次の処理が行われます。  <br/> Skype for Business Online ユーザーの場合: サインイン失敗ログは自動的にアップロードされます。 Skype for Business オンプレミスユーザーの場合: アップロードする前に、確認のダイアログボックスがユーザーに表示されます。 この設定を無効にすると、skype for Business オンプレミスと Skype for business Online の両方のユーザーのサインインログが Skype for business Server に自動的にアップロードされます。 この設定を有効にした場合、サインインログは自動的にアップロードされることはありません。  <br/> |
|SIP 接続の HTTP フォールバックを無効にする (DisableHttpConnect)  <br/> |TLS または TCP が使用できない場合、Skype for Business Server が HTTP を使用してサーバーに接続できないようにします。 既定では、Skype for Business は最初に TLS または TCP を使用してサーバーに接続しようとし、次のどちらのトランスポート方法も成功しない場合、Skype for Business は HTTP を使用して接続しようとします。 このポリシーは、フォールバックの HTTP 接続試行を無効にするために使用します。  <br/> |
|ログオン資格情報を要求する (DisableNTCredentials)  <br/> |ユーザーは、SIP サーバーへのサインイン時に Windows 資格情報を自動的に使用するのではなく、Skype for Business のログオン資格情報を提供する必要があります。  <br/> |
|サーバーバージョンチェックを無効にする (DisableServerCheck)  <br/> |このポリシーを1に設定すると、Skype for Business がサインイン前にサーバー名とバージョンを確認できなくなります。 既定では、Skype for Business はサインインする前にこれらのチェックを行います。  <br/> |
|アドレス帳サービスファイルをダウンロードするために BITS を使用できるようにする (EnableBitsForGalDownload)  <br/> |Skype for Business でバックグラウンドインテリジェント転送サービス (BITS) を使用して、アドレス帳サービスのファイルをダウンロードできるようにします。  <br/> |
|SIP セキュリティモードを構成する (EnableSIPHighSecurityMode)  <br/> |Skype for Business でインスタントメッセージをより安全に送受信できるようにします。 このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。  <br/> このポリシー設定を構成しない場合、Skype for Business では任意のトランスポートを使用できます。 ただし、TLS を使用せず、サーバーがユーザーを認証する場合、Skype for Business では NTLM 認証または Kerberos 認証のいずれかを使用する必要があります。  <br/> |
|グローバルアドレス帳のダウンロードの初期遅延 (GalDownloadInitialDelay)  <br/> |グローバルアドレス一覧 (GAL) がダウンロードされるまでの期間を指定します。 既定値は60分です。これは、サーバーが0から60分の間のランダムな期間、GAL ファイルのダウンロードを遅延させることを意味します。  <br/> |
|ユーザーが Skype for Business を実行できないようにする (PreventRun)  <br/> |ユーザーが Skype for Business を実行できないようにします。 このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。  <br/> |
|ユーザーパスワードの保存を許可する (SavePassword)  <br/> |Skype for Business がパスワードを保存できるようにします。  <br/> |
|SIP 圧縮モードを構成する (SipCompression)  <br/> |SIP 圧縮を有効にするタイミングを指定します。 既定では、SIP 圧縮はアダプターの速度に基づいて有効になっています。 このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。  <br/> |
|信頼されたドメインリスト (TrustModelData)  <br/> |顧客 SIP ドメインのプレフィックスに一致しない信頼されたドメインを一覧表示します。  <br/> |
   
サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。
  
**グループ ポリシーの優先順位**

|**Precedence**|**設定の場所と方法**|
|:-----|:-----|
|1   <br/> |Skype for Business Server のインバンドプロビジョニング  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Skype for Business の [オプション] ダイアログボックス  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Skype for Business 管理用テンプレートファイルを使用してグループポリシー設定を定義するには

1. すべての言語に依存しない ADMX ファイルを含むルートレベルのフォルダーを作成します。 たとえば、次の場所で、ドメインコントローラーの中央ストアのルートフォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > この手順では、ドメイン内の複数のコンピューターを管理することを前提としています。 この場合は、プライマリドメインコントローラーの Sysvol フォルダーにある中央ストアにテンプレートを格納します。 これはドメインの管理用テンプレートのためのレプリケートされた集中格納場所となります。 
  
2. 使用する言語ごとにサブフォルダーを作成します。 これらのサブフォルダーには、言語固有の ADML リソースファイルが含まれています。 たとえば、次の場所に米国英語 (EN-US) のサブフォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

