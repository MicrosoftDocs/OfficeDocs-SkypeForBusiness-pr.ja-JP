---
title: Cloud Connector コマンドレットのリファレンス
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 次の表に、Skype for Business Cloud Connector エディションのコマンドレットを簡単な説明と共に一覧表示し、詳細情報へのリンクを示します。
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359053"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector コマンドレットのリファレンス
 
> [!Important]
> Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。 組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。

次の表に、Skype for Business Cloud Connector エディションのコマンドレットを簡単な説明と共に一覧表示し、詳細情報へのリンクを示します。
  
> [!NOTE]
> Cloud Connector ホストコンピューターですべてのコマンドレットを実行する必要があります。また、管理者として PowerShell セッションを実行する必要があります。 
  
|**コマンドレット名**|**Description**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> バージョン1.4.2 以降  <br/> |証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |お客様が提供した Windows Server 2012 R2 ISO ファイルを使用して、ベース仮想ハードディスクファイル (VHDX) を作成します。 VHDX ファイルは、Cloud Connector の展開時に使用されます。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |クラウドコネクタホストサーバーをメンテナンスモードにすることにより、更新プロセスの準備を行います。 アプライアンスは "排出" です。つまり、既存の呼び出しはすべて完了しますが、新しい呼び出しは拒否されます。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Cloud Connector ホストサーバーで更新プログラムのメンテナンスモードを終了します。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Skype for business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホストサーバー上のローカルファイルにエクスポートします。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Cloud connector のサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンスディレクトリにエクスポートします。 展開で使用するファイルを変更したり、名前を変更したりすることができます。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> バージョン1.4.2 以降  <br/> |ルート CA 証明書を Cloud Connector ホストサーバー上のローカルファイルにエクスポートします。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Cloud Connector ホストサーバー上の作業ディレクトリを取得します。 すべての展開ファイルはこのディレクトリに保存されます。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Cloud Connector アプライアンスのログが格納されている現在のディレクトリを示します。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> バージョン2.1 以降  <br/> |Cloud Connector アプライアンスの診断情報を提供します。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |現在の Cloud Connector の展開の資格情報を返します。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |クラウドコネクタ展開の外部証明書ファイルのパスを返します。 ユーザーがこの証明書を準備します。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |サイトレベルの構成ファイルが保存されている現在のディレクトリを示します。 フォルダーには、ベース VHD および Cloud Connector のインストールファイルが含まれています。 このフォルダーは、Cloud Connector サイトの他のすべてのアプライアンスと共有する必要があります。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Cloud Connector のサイトレベルのログが格納されている現在のディレクトリを表示します。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> バージョン2.0 以降  <br/> |Cloud Connector インスタンスのバージョンを返します。 Get-CCVersion は、Cloud Connector のホストマシンでのみ使用できます。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> バージョン2.0 以降  <br/> |Skype for Business Cloud Connector エディションの構成をローカルファイルから Cloud Connector ホストサーバーにインポートします。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |AD、中央管理ストア、仲介サーバー、エッジサーバー仮想マシンなどの Cloud Connector アプライアンスをホストサーバーにインストールします。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 高可用性の情報をオンラインのテナント構成から取得して、ホストサーバー上の Cloud Connector アプライアンスに公開します。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | オンラインテナント構成の PSTN サイトにアプライアンス情報を登録します。 アプライアンスは、Cloud Connector management service で展開および管理する前に登録する必要があります。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> バージョン1.4.2 以降  <br/> |\<SiteRootDirectory\>Cloud Connector のサイト共有ディレクトリの CA フォルダーにある証明機関サービスのバックアップファイル「\CA\SFB CCE Root. p12」を削除します。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> バージョン1.4.2 以降  <br/> |Renew-cccacertificate の実行後、または CcServerCertificate コマンドレットの更新後に、中央管理ストア、仲介サーバー、およびエッジサーバー上のレガシサーバー証明書を削除します。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> バージョン1.4.2 のみ  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> バージョン1.4.2 のみ  <br/> |Cloud Connector の有効期限が近づいているか、既に有効期限が切れている場合に、その証明書を更新します。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> バージョン1.4.2 以降  <br/> |証明機関サーバーをリセットして、新しい証明機関の証明書をインストールします。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> バージョン2.1 以降  <br/> |資格情報をクリーンアップし、現在の Cloud Connector の展開に使用されているすべての資格情報を再入力するように求めるメッセージを表示します。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Cloud Connector アプライアンスのログディレクトリにある着信および発信の通話ログを検索します。  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Cloud Connector ホストサーバー上の作業ディレクトリを設定します。 すべての展開ファイルはこのディレクトリに保存されます。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |現在の Cloud Connector の展開の資格情報を設定します。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |仲介サーバーまたはエッジサーバーの証明書が格納されるパスを指定します。  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Cloud Connector のサイトレベルの構成ファイルが格納されるディレクトリを設定します。 フォルダーには、ベース VHD および Cloud Connector の構成ファイルが格納されます。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Cloud Connector のビットと msi ファイルを同期的にダウンロードします。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Cloud Connector アプライアンスの着信および発信の通話ログを生成します。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Cloud Connector アプライアンスの着信と発信の通話ログの生成を停止します。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |実行中のアプライアンスとスイッチを、新たに展開した、またはバックアップアプライアンスに切断します。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |実行中の Cloud Connector アプライアンスをホストサーバーからアンインストールします。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |オンラインテナント構成の PSTN サイトから現在の Cloud Connector アプライアンスの登録を解除します。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> バージョン2.0 以降  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> バージョン2.0 以降  <br/> |Cloud Connector の有効期限が近づいているか、既に有効期限が切れている場合に、その証明書を更新します。  <br/> |
   

