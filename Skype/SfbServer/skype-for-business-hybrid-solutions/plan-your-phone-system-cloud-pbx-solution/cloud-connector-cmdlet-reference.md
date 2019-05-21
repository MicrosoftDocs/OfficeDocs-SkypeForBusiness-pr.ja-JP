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
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 次の表に、Skype for Business Cloud Connector エディションのコマンドレットとその概要、および詳細情報へのリンクを示します。
ms.openlocfilehash: 58fed82857138bf9716db88648344e9140b29d6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294383"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
次の表に、Skype for Business Cloud Connector エディションのコマンドレットとその概要、および詳細情報へのリンクを示します。
  
> [!NOTE]
> クラウドコネクタホストコンピューター上のすべてのコマンドレットを実行し、管理者として PowerShell セッションを実行する必要があります。 
  
|**コマンドレット名**|**説明**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク ファイル (VHDX) を作成します。VHDX ファイルは、Cloud Connector の展開時に使用されます。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |クラウドコネクタホストサーバーをメンテナンスモードにして、更新プロセスを準備します。 アプライアンスは "排出" です。つまり、既存の通話はすべて完了しますが、新しい通話は拒否されます。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |クラウドコネクタホストサーバーで更新プログラムのメンテナンスモードを終了します。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |クラウドコネクタのサンプル構成ファイル (.ini) をクラウドコネクタのアプライアンスのアプライアンスディレクトリにエクスポートします。 このファイルの名前は、お使いの展開での使用に合わせて変更できます。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> バージョン 1.4.2 以降   <br/> |クラウドコネクタホストサーバー上のローカルファイルにルート CA 証明書をエクスポートします。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |クラウドコネクタホストサーバー上の作業ディレクトリを取得します。 すべての展開ファイルはこのディレクトリに保存されます。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |クラウドコネクタアプライアンスのログが保存されている現在のディレクトリが表示されます。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> バージョン2.1 以降  <br/> |クラウドコネクタアプライアンスの診断情報を提供します。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |現在のクラウドコネクタ展開の資格情報を返します。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |クラウドコネクタ展開用の外部証明書ファイルパスを返します。 この証明書はユーザーが準備します。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 このフォルダーには、基本 VHD と Cloud Connector のインストールファイルが含まれています。 このフォルダーは、クラウドコネクタサイトの他のすべてのアプライアンスと共有する必要があります。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |クラウドコネクタのサイトレベルのログが保存されている現在のディレクトリが表示されます。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector インスタンスでのバージョンを返します。Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> バージョン 2.0 以降  <br/> |ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |AD、サーバーの中央管理ストア、仲介サーバー、エッジサーバー仮想マシンなど、クラウドコネクタのアプライアンスをホストサーバーにインストールします。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | オンラインテナント構成から高可用性情報を取得し、ホストサーバーのクラウドコネクタアプライアンスに公開します。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。 アプライアンスは、クラウドコネクタ管理サービスによって展開および管理される前に、登録する必要があります。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> バージョン 1.4.2 以降  <br/> |クラウドコネクタのサイト共有ディレクトリの下\<に\>ある CA フォルダーで、証明機関サービスのバックアップファイル "SiteRootDirectory \CA\SfB CCE ルート. p12" を削除します。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> バージョン 1.4.2 以降  <br/> |Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |Cloud Connector の証明書を、有効期限が近づいている場合またはすでに有効期限が切れている場合に更新します。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サーバーをリセットして、新しい証明書機関の証明書をインストールします。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> バージョン2.1 以降  <br/> |資格情報をクリーンアップし、現在のクラウドコネクタ展開で使用されているすべての資格情報を再入力するように求めます。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |クラウドコネクタアプライアンスのログディレクトリで、着信通話と発信通話のログを検索します  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |クラウドコネクタホストサーバー上の作業ディレクトリを設定します。 すべての展開ファイルはこのディレクトリに格納されます。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |現在のクラウドコネクタ展開の資格情報を設定します。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |仲介サーバーまたはエッジ サーバーの証明書が格納されているパスを指定します。  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |クラウドコネクタのサイトレベルの構成ファイルが保存されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |クラウドコネクタの bits と msi ファイルを同期的にダウンロードします。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |クラウドコネクタアプライアンスの受信および送信通話ログを生成します。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |クラウドコネクタアプライアンスの受信および送信通話ログの生成を停止します。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |ホストサーバーから実行されているクラウドコネクタアプライアンスをアンインストールします。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |オンラインテナント構成の PSTN サイトから、現在のクラウドコネクタのアプライアンスの登録を解除します。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> バージョン 2.0 以降  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector の証明書を、有効期限が近づいている場合またはすでに有効期限が切れている場合に更新します。  <br/> |
   

