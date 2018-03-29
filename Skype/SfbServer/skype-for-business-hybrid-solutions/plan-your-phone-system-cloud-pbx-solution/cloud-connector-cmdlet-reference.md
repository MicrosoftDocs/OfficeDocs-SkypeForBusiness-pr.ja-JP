---
title: Cloud Connector コマンドレットのリファレンス
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
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector コマンドレットのリファレンス
 
次の表に、Skype for Business Cloud Connector エディションのコマンドレットとその概要、および詳細情報へのリンクを示します。
  
> [!NOTE]
> Cloud Connector のホスト コンピューターですべてのコマンドレットを実行する必要があります。また、管理者として PowerShell セッションを実行する必要があります。 
  
|**コマンドレット名**|**説明**|
|:-----|:-----|
|[バックアップ CcCertificationAuthority](backup-cccertificationauthority.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サービスをファイルにバックアップして、サイト共有ディレクトリの下にある CA フォルダーに保存します。     <br/> |
|[変換 CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |顧客支給の Windows Server 2012 R2 ISO ファイルを使用してベース仮想ハード ディスク ファイル (VHDX) を作成します。VHDX ファイルは、Cloud Connector の展開時に使用されます。  <br/> |
|[入力 CcUpdate](enter-ccupdate.md) <br/> |メンテナンス モードに配置することによって更新プロセスのクラウドのコネクタのホスト サーバーを準備します。 アプライアンスは「放電」です。既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。  <br/> |
|[終了 CcUpdate](exit-ccupdate.md) <br/> |Cloud Connector のホスト サーバーでの更新のメンテナンス モードを終了します。  <br/> |
|[エクスポート CcConfiguration](export-ccconfiguration.md) <br/> | Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 <br/> |
|[エクスポート CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |クラウド コネクタのサンプル構成ファイル (.ini) をクラウド コネクタ アプライアンスのアプライアンスのディレクトリにエクスポートします。 このファイルの名前は、お使いの展開での使用に合わせて変更できます。  <br/> |
|[エクスポート CcRootCertificate](export-ccrootcertificate.md) <br/> バージョン 1.4.2 以降  <br/> |ルート CA 証明書を Cloud Connector のホスト サーバーでのローカル ファイルにエクスポートします。  <br/> |
|[Get CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Cloud Connector のホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに格納されます。  <br/> |
|[Get CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |コネクタのクラウド アプライアンスは、ログが保存されている現在のディレクトリを示しています。  <br/> |
|[Get CcApplianceStatus](get-ccappliancestatus.md) <br/> バージョン 2.1 以降では  <br/> |クラウド コネクタ アプライアンスの診断情報を提供します。  <br/> |
|[Get CcCredential](get-cccredential.md) <br/> |現在の Cloud Connector の展開の資格情報を返します。  <br/> |
|[Get CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Cloud Connector の展開用に外部証明書ファイルのパスを返します。この証明書はユーザーが準備します。  <br/> |
|[Get CcSiteDirectory](get-ccsitedirectory.md) <br/> |サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーには、基本の VHD とクラウドのコネクタのインストール ファイルが含まれています。 クラウド コネクタ サイトの他のすべてのアプライアンスでは、このフォルダーを共有する必要があります。  <br/> |
|[Get CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |クラウド コネクタのサイト レベルのログが保存されている現在のディレクトリを示しています。  <br/> |
|[Get CcVersion](get-ccversion.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector インスタンスでのバージョンを返します。Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。  <br/> |
|[インポート-CcConfiguration](import-ccconfiguration.md) <br/> バージョン 2.0 以降  <br/> |クラウド コネクタのホスト サーバーにローカル ファイルから、Skype ビジネス クラウド コネクタのエディション構成をインポートします。  <br/> |
|[インストール CcAppliance](install-ccappliance.md) <br/> |クラウド コネクタ アプライアンスをインストールする-など、AD 中央管理ストア、仲介サーバー、およびエッジ サーバーの仮想マシン、ホスト サーバー上。  <br/> |
|[発行 CcAppliance](publish-ccappliance.md) <br/> | オンライン テナント構成の高可用性の情報を取得し、コネクタのクラウド アプライアンス ホスト サーバー上に公開します。 <br/> |
|[登録 CcAppliance](register-ccappliance.md) <br/> | アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。 展開し、クラウド管理サービスによって管理されていることができます前に、アプライアンスを登録してください。 <br/> |
|[削除 CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サービスのバックアップ ファイルを削除"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"クラウド コネクタのサイトの共有ディレクトリにある CA のフォルダーにします。  <br/> |
|[削除 CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> バージョン 1.4.2 以降  <br/> |Renew-CcCACertificate または Renew CcServerCertificate コマンドレットの実行後に、中央管理ストア、仲介サーバーおよびエッジ サーバー上にあるレガシー サーバーの証明書を削除します。  <br/> |
|[更新 CcCACertificate](renew-cccacertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[更新 CcServerCertificate](renew-ccservercertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |Cloud Connector の証明書を、有効期限が近づいている場合またはすでに有効期限が切れている場合に更新します。  <br/> |
|[リセット CcCACertificate](reset-cccacertificate.md) <br/> バージョン 1.4.2 以降  <br/> |新しい証明機関の証明書をインストールするのには、証明機関サーバーをリセットします。  <br/> |
|[復元 CcCredentials](restore-cccredentials.md) <br/> バージョン 2.1 以降では  <br/> |資格情報を消去して、現在のクラウドのコネクタの配置に使用するすべての資格情報を再入力するように求められます。  <br/> |
|[検索 CcLog](search-cclog.md) <br/> |Cloud Connector のアプライアンス ログ ディレクトリで着信および発信の通話ログを検索します  <br/> |
|[セット CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |クラウド コネクタのホスト サーバー上の作業ディレクトリを設定します。 すべての展開ファイルはこのディレクトリに保存されます。  <br/> |
|[セット CcCredential](set-cccredential.md) <br/> |現在の Cloud Connector の展開の資格情報を設定します。  <br/> |
|[セット CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |仲介サーバーまたはエッジ サーバーの証明書が格納されているパスを指定します。  <br/> |
|[セット CcSiteDirectory](set-ccsitedirectory.md) <br/> |Cloud Connector のサイト レベルの設定ファイルが格納されるディレクトリを設定します。フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。  <br/> |
|[開始 CcDownload](start-ccdownload.md) <br/> |クラウド コネクタのビットと msi ファイルを同期的にダウンロードします。  <br/> |
|[開始 CcLogging](start-cclogging.md) <br/> |クラウド コネクタ アプライアンスの着信および発信呼び出しのログを生成します。  <br/> |
|[Stop CcLogging](stop-cclogging.md) <br/> |クラウド コネクタ アプライアンスの通話記録を生成、受信と送信を停止します。  <br/> |
|[スイッチ CcVersion](switch-ccversion.md) <br/> |実行中のアプライアンスとスイッチの、新規に展開されたアプライアンスまたはバックアップ インスタンスへの接続を切断します。  <br/> |
|[アンインストール CcAppliance](uninstall-ccappliance.md) <br/> |実行中のコネクタのクラウド アプライアンスをホスト サーバーからアンインストールします。  <br/> |
|[登録解除 CcAppliance](unregister-ccappliance.md) <br/> |オンライン テナント構成では、PSTN のサイトから現在のクラウド コネクタ アプライアンスを登録解除します。  <br/> |
|[更新 CcCACertificate](update-cccacertificate.md) <br/> バージョン 2.0 以降  <br/> |証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。  <br/> |
|[更新 CcServerCertificate](update-ccservercertificate.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector の証明書を、有効期限が近づいている場合またはすでに有効期限が切れている場合に更新します。  <br/> |
   

