---
title: クライアント ブートストラップ ポリシーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: '概要: グループポリシーを管理する方法について説明します。'
ms.openlocfilehash: 5d099a57db720a87e67ee00aa87a8613ac6552b7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234497"
---
# <a name="configure-client-bootstrapping-policies"></a>クライアント ブートストラップ ポリシーの構成
 
**概要:** グループポリシーを管理する方法を説明します。
  
グループ ポリシー管理コンソール (GPMC) とグループ ポリシー オブジェクト エディターは、グループ ポリシーを管理するために使用するツールです。 Office グループポリシー管理用テンプレートに含まれている lync16 (ADMX) および adml (ADML) 管理用テンプレートには、ドメインのグループポリシーオブジェクト用に構成した Skype for Business のレジストリベースのポリシー設定が含まれています。 ADML ファイルは、ADMX ファイルに対する言語固有の補完ファイルです。 それぞれの ADMX および ADML ファイルには、単一の Office アプリケーションに関するポリシー設定が含まれています。 Microsoft ダウンロードセンターから[、Office 2016 管理用テンプレートファイル (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030)を無料でダウンロードできます。
  
Skype for Business クライアントの場合は、いくつかのクライアントブートストラップポリシーがあり、ユーザーが初めてサーバーにサインインする前に構成することを検討してください。 たとえば、サインインが完了するまでクライアントで使用する既定のサーバーとセキュリティモードなどです。 グループポリシーを使って、ユーザーのコンピューターのレジストリでこれらの設定を行ってから、サインインして、サーバーからインバンドのプロビジョニング設定を受信することができます。 次の表に、Skype for Business で利用できるグループポリシー設定を示します。
  
**Skype for Business のグループポリシー設定**

|グループ ポリシー設定|説明|
|:-----|:-----|
|サーバーの指定 (ConfigurationMode)  <br/> | Skype for Business が、サインイン中に使用するトランスポートとサーバーを識別する方法を指定します。 この設定では、次の値を指定します。 <br/>  ServerAddressExternal: 外部ファイアウォールの外側からの接続時に、フェデレーションからの連絡先とクライアントで使用されるサーバー名または IP アドレスを指定します。 <br/>  ServerAddressInternal: クライアントが組織のファイアウォール内から接続するときに使用されるサーバー名または IP アドレスを指定します。 <br/>  Transport: 伝送制御プロトコル (TCP) またはトランスポート層セキュリティ (TLS) のいずれかを指定します。 <br/> |
|サポートされているその他のサーバーバージョン (ConfiguredServerCheckValues)  <br/> |既定でサポートされているサーバーのバージョンに加えて、サーバーのバージョン名のリストを、Skype for Business Server がログオンするときのセミコロンで区切って指定します。  <br/> |
|サインイン失敗ログの自動アップロードを無効にする (DisableAutomaticSendTracing)  <br/> |サインインエラーログを Skype for Business Server に自動的にアップロードして、分析します。 サインインが成功した場合は、ログは自動的にアップロードされません。 このポリシーが構成されていない場合は、次のように動作します。  <br/> Skype for Business Online ユーザーの場合: サインインエラーログは、自動的にアップロードされます。 Skype for Business オンプレミスユーザーの場合: アップロードの前に、確認のダイアログボックスがユーザーに表示されます。 この設定を無効にすると、サインインログは、skype for business オンプレミスと Skype for business Online の両方の skype for Business Server に自動的にアップロードされます。 この設定を有効にすると、サインインログが自動的にアップロードされることはありません。  <br/> |
|SIP 接続の HTTP フォールバックを無効にする (DisableHttpConnect)  <br/> |TLS または TCP が利用できない場合、Skype for Business Server が HTTP を使用してサーバーに接続しようとすることを防止します。 既定では、Skype for Business は最初に TLS または TCP を使用してサーバーに接続しようとし、どちらのトランスポート方法も成功しない場合、Skype for Business は HTTP を使用して接続を試みます。 このポリシーを使用して、フォールバック HTTP 接続の試行を無効にします。  <br/> |
|ログオン資格情報を要求する (DisableNTCredentials)  <br/> |SIP サーバーへのサインイン時に、ユーザーが Skype for Business のログオン資格情報を使用して、Windows の資格情報を自動的に使用しないようにする必要があります。  <br/> |
|サーバーのバージョンチェックを無効にする (DisableServerCheck)  <br/> |このポリシーを1に設定すると、Skype for Business が、サインイン前にサーバー名とバージョンを確認できなくなります。 既定では、Skype for Business でサインイン前にこれらのチェックが行われます。  <br/> |
|BITS を使用してアドレス帳サービスファイル (EnableBitsForGalDownload) をダウンロードできるようにする  <br/> |Skype for Business がバックグラウンドインテリジェント転送サービス (BITS) を使用して、アドレス帳サービスファイルをダウンロードできるようにします。  <br/> |
|SIP セキュリティモード (EnableSIPHighSecurityMode) を構成する  <br/> |Skype for Business がインスタントメッセージの送受信をより安全に行えるようにします。 このポリシーは、Windows .NET または Microsoft Exchange Server サービスに対して無効です。  <br/> このポリシー設定を構成しないと、Skype for Business はどのトランスポートでも使用できます。 ただし、TLS を使用せず、サーバーがユーザーを認証する場合は、Skype for Business で NTLM 認証または Kerberos 認証を使用する必要があります。  <br/> |
|グローバルアドレス帳のダウンロードの最初の遅延 (GalDownloadInitialDelay)  <br/> |グローバル アドレス一覧 (GAL) のダウンロードが始まるまでの時間を指定します。既定値は 60 分です。つまり、サーバーでは GAL ファイルのダウンロードがランダムに 0 ～ 60 分間延期されます。  <br/> |
|ユーザーが Skype for Business (PreventRun) を実行できないようにする  <br/> |ユーザーが Skype for Business を実行できないようにします。 このポリシー設定は、コンピューターの構成とユーザーの構成の両方で構成できますが、コンピューターの構成のポリシー設定が優先されます。  <br/> |
|ユーザーパスワードの保存を許可する (保存パスワード)  <br/> |Skype for Business でパスワードを保存できるようにします。  <br/> |
|SIP 圧縮モード (SipCompression) を構成する  <br/> |SIP 圧縮をオンにするときを定義します。既定では、アダプターのスピードに基づいて SIP 圧縮が有効化されます。このポリシーを設定すると、サインインの時間が長くなる可能性があることに注意してください。  <br/> |
|信頼されたドメインリスト (TrustModelData)  <br/> |ユーザーの SIP ドメインのプレフィックスに一致しない信頼されたドメインをリストします。  <br/> |
   
サーバー上で構成されたポリシーは、ユーザーによって構成されたグループ ポリシー設定やクライアント オプションよりも優先されます。次の表に、競合が発生した場合の設定の優先順位をまとめます。
  
**グループ ポリシーの優先順位**

|**優先順位**|**設定の場所と方法**|
|:-----|:-----|
|1  <br/> |Skype for Business Server のインバンドプロビジョニング  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Skype for Business の [オプション] ダイアログボックス  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Skype for Business 管理用テンプレートファイルを使用してグループポリシー設定を定義するには

1. 言語に依存しないすべての ADMX ファイルを含めるルートレベル フォルダーを作成します。たとえば、ドメイン コントローラーの次の場所で、中央ストア用のルート フォルダーを作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > この手順では、ドメインで複数のコンピューターを管理することを想定しています。この場合、テンプレートをプライマリ ドメイン コントローラーの Sysvol フォルダーにある中央ストアに保存します。これにより、ドメインの管理用テンプレート用のレプリケートされた中央の保存場所が提供されます。 
  
2. 使用する各言語用のサブフォルダーを作成します。 これらのサブフォルダーには、言語固有の ADML リソース ファイルが含められます。 たとえば、米国英語 (EN-US) 用のサブフォルダーを次の場所で作成します。
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

