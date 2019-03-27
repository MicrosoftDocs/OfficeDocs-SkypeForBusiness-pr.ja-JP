---
title: Cloud Connector コマンドレットのリファレンス
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 次の表に、Skype for Business Cloud Connector エディションのコマンドレットとその概要、および詳細情報へのリンクを示します。
ms.openlocfilehash: aa8b8ebe4ffd7d1cb2c405eae5fe6604c5f4c378
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896722"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
次の表に、Skype for Business Cloud Connector エディションのコマンドレットとその概要、および詳細情報へのリンクを示します。
  
> [!NOTE]
> クラウド コネクタのホスト ・ マシン上のすべてのコマンドレットを実行する必要があり、管理者として PowerShell セッションを実行する必要があります。 
  
|**コマンドレット名**|**説明**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク ファイル (VHDX) を作成します。VHDX ファイルは、Cloud Connector の展開時に使用されます。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |メンテナンス モードに配置することによって更新プロセスのクラウドのコネクタのホスト サーバーを準備します。 アプライアンスは「放電」です。既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |クラウド コネクタのホスト サーバー上でメンテナンス モードを終了するに更新します。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |クラウド コネクタのサンプル構成ファイル (.ini) をクラウド コネクタ アプライアンスのアプライアンスのディレクトリにエクスポートします。 このファイルの名前は、お使いの展開での使用に合わせて変更できます。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> バージョン 1.4.2 以降   <br/> |クラウド コネクタのホスト サーバー上のローカル ファイルには、ルート CA 証明書をエクスポートします。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |クラウド コネクタのホスト サーバー上の作業ディレクトリを取得します。 すべての展開ファイルはこのディレクトリに保存されます。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |コネクタのクラウド アプライアンスは、ログが保存されている現在のディレクトリを示しています。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> バージョン 2.1 以降では  <br/> |クラウド コネクタ アプライアンスの診断情報を提供します。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |現在のクラウドのコネクタの配置の資格情報を返します。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |クラウドのコネクタの配置の外部の証明書ファイルのパスを返します。 この証明書はユーザーが準備します。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーには、基本の VHD とクラウドのコネクタのインストール ファイルが含まれています。 クラウド コネクタ サイトの他のすべてのアプライアンスでは、このフォルダーを共有する必要があります。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |クラウド コネクタのサイト レベルのログが保存されている現在のディレクトリを示しています。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector インスタンスでのバージョンを返します。Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> バージョン 2.0 以降  <br/> |クラウド コネクタのホスト サーバーにローカル ファイルから、Skype ビジネス クラウド コネクタのエディション構成をインポートします。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |クラウド コネクタ アプライアンスをインストールする-など、AD 中央管理ストア、仲介サーバー、およびエッジ サーバーの仮想マシン、ホスト サーバー上。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | オンライン テナント構成の高可用性の情報を取得し、コネクタのクラウド アプライアンス ホスト サーバー上に公開します。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。 展開し、クラウド管理サービスによって管理されていることができます前に、アプライアンスを登録してください。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サービスのバックアップ ファイルを削除"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"クラウド コネクタのサイトの共有ディレクトリにある CA のフォルダーにします。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> バージョン 1.4.2 以降  <br/> |Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |Cloud Connector の証明書を、有効期限が近づいている場合またはすでに有効期限が切れている場合に更新します。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サーバーをリセットして、新しい証明書機関の証明書をインストールします。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> バージョン 2.1 以降では  <br/> |資格情報を消去して、現在のクラウドのコネクタの配置に使用するすべての資格情報を再入力するように求められます。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |クラウド コネクタ アプライアンス ・ ログ ・ ディレクトリに検索、着信および発信呼び出しの記録します。  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |クラウド コネクタのホスト サーバー上の作業ディレクトリを設定します。 すべての展開ファイルはこのディレクトリに格納されます。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |現在のクラウドのコネクタの配置の資格情報を設定します。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |仲介サーバーまたはエッジ サーバーの証明書が格納されているパスを指定します。  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |クラウド コネクタのサイト レベルの構成ファイルを保存するディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |クラウド コネクタのビットと msi ファイルを同期的にダウンロードします。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |クラウド コネクタ アプライアンスの着信および発信呼び出しのログを生成します。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |クラウド コネクタ アプライアンスの通話記録を生成、受信と送信を停止します。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |実行中のコネクタのクラウド アプライアンスをホスト サーバーからアンインストールします。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |オンライン テナント構成では、PSTN のサイトから現在のクラウド コネクタ アプライアンスを登録解除します。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> バージョン 2.0 以降  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector の証明書を、有効期限が近づいている場合またはすでに有効期限が切れている場合に更新します。  <br/> |
   

