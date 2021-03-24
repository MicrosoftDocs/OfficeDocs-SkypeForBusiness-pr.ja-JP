---
title: クラウド コネクタ コマンドレットのリファレンス
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
description: 次の表に、Skype for Business Cloud Connector Edition コマンドレットの概要と詳細へのリンクを示します。
ms.openlocfilehash: 3739518dd8ddcd17bce8108228d0d643ebaa79a4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092935"
---
# <a name="cloud-connector-cmdlet-reference"></a>クラウド コネクタ コマンドレットのリファレンス
 
> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

次の表に、Skype for Business Cloud Connector Edition コマンドレットの概要と詳細へのリンクを示します。
  
> [!NOTE]
> すべてのコマンドレットを Cloud Connector ホスト コンピューターで実行し、PowerShell セッションを管理者として実行する必要があります。 
  
|**コマンドレット名**|**Description**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの CA フォルダーに保存します。     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |R2 ISO ファイルから提供された顧客を使用して、基本仮想ハード ディスク ファイル (VHDX) Windows Server 2012作成します。 VHDX ファイルは、クラウド コネクタの展開中に使用されます。  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |クラウド コネクタ ホスト サーバーをメンテナンス モードにすることで、更新プロセス用に準備します。 アプライアンスは "ドレイン" です。つまり、既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Cloud Connector ホスト サーバーの更新メンテナンス モードを終了します。  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Skype for Business Cloud Connector Edition 構成を Skype for Business Cloud Connector Edition ホスト サーバー上のローカル ファイルにエクスポートします。 <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |クラウド コネクタ のサンプル構成ファイル (.ini) をクラウド コネクタ アプライアンスのアプライアンス ディレクトリにエクスポートします。 展開に使用するファイルを変更して名前を変更できます。  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> バージョン 1.4.2 以降  <br/> |ルート CA 証明書をクラウド コネクタ ホスト サーバー上のローカル ファイルにエクスポートします。  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |クラウド コネクタ ホスト サーバー上の作業ディレクトリを取得します。 すべての展開ファイルは、このディレクトリに格納されます。  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |クラウド コネクタ アプライアンスのログが格納されている現在のディレクトリを表示します。  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> バージョン 2.1 以降  <br/> |クラウド コネクタ アプライアンスの診断情報を提供します。  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |現在のクラウド コネクタ展開の資格情報を返します。  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |クラウド コネクタ展開の外部証明書ファイル パスを返します。 ユーザーは、この証明書を準備します。  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |サイト レベル構成ファイルが格納されている現在のディレクトリを表示します。 フォルダーには、基本 VHD とクラウド コネクタのインストール ファイルが含まれる。 このフォルダーは、クラウド コネクタ サイトの他のすべてのアプライアンスと共有する必要があります。  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |クラウド コネクタのサイト レベル ログが格納されている現在のディレクトリを表示します。  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector インスタンスのバージョンを返します。 Get-CCVersionは、クラウド コネクタのホスト コンピューターでのみ使用できます。  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> バージョン 2.0 以降  <br/> |Skype for Business Cloud Connector Edition 構成をローカル ファイルからクラウド コネクタ ホスト サーバーにインポートします。  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |クラウド コネクタ アプライアンス (AD、中央管理ストア、仲介サーバー、エッジ サーバーの仮想マシンを含む) をホスト サーバーにインストールします。  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | オンライン テナント構成から高可用性情報を取得し、ホスト サーバー上のクラウド コネクタ アプライアンスに発行します。 <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | オンライン テナント構成で PSTN サイトにアプライアンス情報を登録します。 アプライアンスをクラウド コネクタ管理サービスによって展開および管理するには、その前にアプライアンスを登録する必要があります。 <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> バージョン 1.4.2 以降  <br/> |クラウド コネクタのサイト共有ディレクトリの CA フォルダーにある証明機関サービス バックアップ ファイル \<SiteRootDirectory\> "\CA\SfB CCE Root.p12" を削除します。  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> バージョン 1.4.2 以降  <br/> |サーバーの全体管理ストア、仲介サーバー、およびエッジ サーバーの従来のサーバー証明書は、CcServerCertificate コマンドレットまたは更新 CcServerCertificate コマンドレットを実行した後Renew-CcCACertificate削除します。  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |証明機関サービス サーバーを再インストールAD新しいルート CA 証明書を作成します。  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> バージョン 1.4.2 のみ  <br/> |Cloud Connector の証明書の有効期限が近い場合、または既に有効期限が切れている場合は、証明書を更新します。  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> バージョン 1.4.2 以降  <br/> |証明機関サーバーをリセットして、新しい証明機関証明書をインストールします。  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> バージョン 2.1 以降  <br/> |資格情報をクリーンアップし、現在のクラウド コネクタ展開で使用されている資格情報を再入力するように求めるメッセージが表示されます。  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |クラウド コネクタ アプライアンス ログ ディレクトリ内の着信および発信の通話ログを検索します。  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |クラウド コネクタ ホスト サーバー上の作業ディレクトリを設定します。 すべての展開ファイルは、このディレクトリに格納されます。  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |現在のクラウド コネクタ展開の資格情報を設定します。  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |仲介サーバーまたはエッジ サーバーの証明書が格納されるパスを指定します。  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |クラウド コネクタのサイト レベル構成ファイルが格納されるディレクトリを設定します。 フォルダーには、基本 VHD とクラウド コネクタ構成ファイルが含まれる。  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |クラウド コネクタ ビットと msi ファイルを同期的にダウンロードします。  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |クラウド コネクタ アプライアンスの着信および発信通話ログを生成します。  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |クラウド コネクタ アプライアンスの着信および発信通話ログの生成を停止します。  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |実行中のアプライアンスを切断し、新しく展開されたアプライアンスまたはバックアップ アプライアンスに切り替します。  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |実行中のクラウド コネクタ アプライアンスをホスト サーバーからアンインストールします。  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |オンライン テナント構成の PSTN サイトから現在のクラウド コネクタ アプライアンスの登録を解除します。  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> バージョン 2.0 以降  <br/> |証明機関サービス サーバーを再インストールAD新しいルート CA 証明書を作成します。  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> バージョン 2.0 以降  <br/> |Cloud Connector の証明書の有効期限が近い場合、または既に有効期限が切れている場合は、証明書を更新します。  <br/> |
