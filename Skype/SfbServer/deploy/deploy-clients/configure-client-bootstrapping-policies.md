---
title: クライアント ブートストラップ ポリシーの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: '概要: グループ ポリシーを管理する方法。'
ms.openlocfilehash: 5d5a2d3a7939f34bb42995bb69280fb7891736ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805987"
---
# <a name="configure-client-bootstrapping-policies"></a>クライアント ブートストラップ ポリシーの構成
 
**概要:** グループ ポリシーを管理する方法。
  
グループ ポリシー管理コンソール (GPMC) とグループ ポリシー オブジェクト エディターは、グループ ポリシーの管理に使用するツールです。 Office グループ ポリシー管理用テンプレートには、lync16.admx (ADMX) および .adml (ADML) 管理用テンプレートが含まれています。このテンプレートには、ドメイン内のグループ ポリシー オブジェクト用に構成する Skype for Business のレジストリ ベースのポリシー設定が含まれます。 ADML ファイルは、ADMX ファイルを補完する言語固有のファイルです。 各 ADMX ファイルと ADML ファイルには、1 つのアプリケーションアプリケーションのポリシー Officeがあります。 Office [2016 管理用テンプレート ファイル (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) は、Microsoft ダウンロード センターから無料でダウンロードできます。
  
Skype for Business クライアントの場合、ユーザーが初めてサーバーにサインインする前に構成を検討する必要があるいくつかのクライアント ブートストラップ ポリシーがあります。 たとえば、サインインが完了するまでクライアントが使用する必要がある既定のサーバーとセキュリティ モードなどです。 グループ ポリシーを使用すると、ユーザーがサインインしてサーバーからのインバンド プロビジョニング設定の受信を開始する前に、ユーザーのコンピューター レジストリでこれらの設定を確立できます。 次の表に、Skype for Business で使用できるグループ ポリシー設定を示します。
  
**Skype for Business のグループ ポリシー設定**

|グループ ポリシー設定|説明|
|:-----|:-----|
|サーバーを指定する (ConfigurationMode)  <br/> | サインイン時に使用するトランスポートとサーバーを Skype for Business で識別する方法を指定します。 この設定では、次の項目を指定します。 <br/>  ServerAddressExternal: 外部ファイアウォールの外側から接続するときに、クライアントおよびフェデレーション連絡先によって使用されるサーバー名または IP アドレスを指定します。 <br/>  ServerAddressInternal: クライアントが組織のファイアウォールの内側から接続するときに使用するサーバー名または IP アドレスを指定します。 <br/>  トランスポート: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のいずれかを指定します。 <br/> |
|サポートされているその他のサーバーバージョン (ConfiguredServerCheckValues)  <br/> |既定でサポートされているサーバー バージョンに加えて、Skype for Business Server がログオンするサーバー バージョン名の一覧をセミコロンで区切って指定します。  <br/> |
|サインイン失敗ログの自動アップロードを無効にする (DisableAutomaticSendTracing)  <br/> |サインイン失敗ログを分析のために Skype for Business Server に自動的にアップロードします。 サインインが成功した場合、ログは自動的にアップロードされません。 このポリシーが構成されていない場合は、次のことが実行されます。  <br/> Skype for Business Online ユーザーの場合: サインイン失敗ログが自動的にアップロードされます。 Skype for Business オンプレミス ユーザーの場合: アップロード前に確認ダイアログ ボックスがユーザーに表示されます。 この設定を無効にすると、Skype for Business オンプレミスユーザーと Skype for Business Online ユーザーの両方について、サインイン ログが Skype for Business Server に自動的にアップロードされます。 この設定を有効にすると、サインイン ログは自動的にアップロードされません。  <br/> |
|SIP 接続の HTTP フォールバックを無効にする (DisableHttpConnect)  <br/> |TLS または TCP が使用できない場合に、Skype for Business Server が HTTP を使用してサーバーに接続しようとしようとして回避します。 既定では、Skype for Business は最初に TLS または TCP を使用してサーバーへの接続を試み、どちらのトランスポート方法も成功しなかった場合、Skype for Business は HTTP を使用して接続を試行します。 このポリシーは、フォールバックの HTTP 接続試行を無効にするために使用します。  <br/> |
|ログオン資格情報を要求する (DisableNTCredentials)  <br/> |SIP サーバーへのサインイン時に Windows 資格情報を自動的に使用するのではなく、Skype for Business のログオン資格情報を入力する必要があります。  <br/> |
|サーバーのバージョン チェックを無効にする (DisableServerCheck)  <br/> |このポリシーを 1 に設定すると、サインインする前に Skype for Business がサーバー名とバージョンを確認できません。 既定では、Skype for Business はサインインする前にこれらのチェックを行います。  <br/> |
|BITS を使用してアドレス帳サービス ファイルをダウンロードする (EnableBitsForGalDownload)  <br/> |Skype for Business でバックグラウンド インテリジェント転送サービス (BITS) を使用してアドレス帳サービス ファイルをダウンロードできます。  <br/> |
|SIP セキュリティ モードを構成する (EnableSIPHighSecurityMode)  <br/> |Skype for Business でインスタント メッセージの送受信を安全に行う。 このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。  <br/> このポリシー設定を構成しない場合、Skype for Business は任意のトランスポートを使用できます。 ただし、TLS を使用しない場合、およびサーバーがユーザーを認証する場合、Skype for Business は NTLM 認証または Kerberos 認証のどちらかを使用する必要があります。  <br/> |
|グローバル アドレス帳のダウンロードの初期遅延 (GalDownloadInitialDelay)  <br/> |グローバル アドレス一覧 (GAL) のダウンロードが行われる前の期間を指定します。 既定値は 60 分です。つまり、サーバーは GAL ファイルのダウンロードを 0 ~ 60 分のランダムな期間遅延します。  <br/> |
|ユーザーによる Skype for Business の実行を防止する (PreventRun)  <br/> |ユーザーが Skype for Business を実行するのを防ぐ。 このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。  <br/> |
|ユーザー パスワードの保存を許可する (SavePassword)  <br/> |Skype for Business でパスワードを保存できます。  <br/> |
|SIP 圧縮モードを構成する (SipCompression)  <br/> |SIP 圧縮を有効にする時間を指定します。 既定では、アダプターの速度に基づいて SIP 圧縮が有効になります。 このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。  <br/> |
|信頼されたドメインリスト (TrustModelData)  <br/> |顧客の SIP ドメインのプレフィックスと一致しない信頼されたドメインを一覧表示します。  <br/> |
   
サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。
  
**グループ ポリシーの優先順位**

|**Precedence**|**設定の場所と方法**|
|:-----|:-----|
|1   <br/> |Skype for Business Server インバンド プロビジョニング  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Skype for Business の [オプション] ダイアログ ボックス  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Skype for Business 管理用テンプレート ファイルを使用してグループ ポリシー設定を定義するには

1. ルート レベルのフォルダーを作成して、言語に依存しないすべての ADMX ファイルを格納します。 たとえば、次の場所にあるドメイン コントローラーの中央ストアのルート フォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > この手順では、ドメイン内の複数のコンピューターを管理する必要がある場合を想定しています。 この場合は、テンプレートをプライマリ ドメイン コントローラーの Sysvol フォルダーの中央ストアに格納します。 これはドメインの管理用テンプレートのためのレプリケートされた集中格納場所となります。 
  
2. 使用する言語ごとにサブフォルダーを作成します。 これらのサブフォルダーには、言語固有の ADML リソース ファイルが含まれる場合があります。 たとえば、次の場所に英語 (EN-US) の米国のサブフォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

