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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 次の表に、Skype for Business クラウド コネクタ エディション コマンドレットの簡単な説明と詳細情報へのリンクを示します。
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676169"
---
# <a name="cloud-connector-cmdlet-reference"></a>クラウド コネクタ コマンドレットのリファレンス

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織がTeamsにアップグレードしたら、[ダイレクト ルーティング](/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミステレフォニー ネットワークをTeamsに接続する方法について説明します。

次の表に、Skype for Business クラウド コネクタ エディション コマンドレットの簡単な説明と詳細情報へのリンクを示します。
  
> [!NOTE]
> Cloud Connector ホスト コンピューターですべてのコマンドレットを実行し、PowerShell セッションを管理者として実行する必要があります。 
  
|コマンドレット名**|説明|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> バージョン 1.4.2 以降|証明機関サービスをファイルにバックアップし、サイト共有ディレクトリの下の CA フォルダーに保存します。|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|お客様から提供された R2 ISO ファイルを使用して、基本仮想ハード ディスク ファイル (VHDX) Windows Server 2012作成します。 VHDX ファイルは、Cloud Connector のデプロイ中に使用されます。|
|[Enter-CcUpdate](enter-ccupdate.md)|Cloud Connector ホスト サーバーをメンテナンス モードにして、更新プロセス用に準備します。 アプライアンスは "ドレイン済み" です。つまり、既存のすべての呼び出しは完了しますが、新しい呼び出しは拒否されます。|
|[Exit-CcUpdate](exit-ccupdate.md)|Cloud Connector ホスト サーバーの更新メンテナンス モードを終了します。|
|[Export-CcConfiguration](export-ccconfiguration.md)|Skype for Business クラウド コネクタ エディション構成を、Skype for Business クラウド コネクタ エディション ホスト サーバー上のローカル ファイルにエクスポートします。|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Cloud Connector のサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。 デプロイに使用するファイルを変更したり、名前を変更したりできます。|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> バージョン 1.4.2 以降|ルート CA 証明書を Cloud Connector ホスト サーバー上のローカル ファイルにエクスポートします。|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Cloud Connector ホスト サーバー上の作業ディレクトリを取得します。 すべてのデプロイ ファイルは、このディレクトリに格納されます。|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Cloud Connector アプライアンスのログが格納されている現在のディレクトリを示します。|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> バージョン 2.1 以降|Cloud Connector アプライアンスの診断情報を提供します。|
|[Get-CcCredential](get-cccredential.md)|現在の Cloud Connector デプロイの資格情報を返します。|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Cloud Connector デプロイの外部証明書ファイル パスを返します。 ユーザーはこの証明書を準備します。|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|サイト レベルの構成ファイルが格納されている現在のディレクトリを示します。 フォルダーには、ベース VHD と Cloud Connector のインストール ファイルが含まれています。 このフォルダーは、Cloud Connector サイトの他のすべてのアプライアンスと共有する必要があります。|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Cloud Connector のサイト レベルログが格納されている現在のディレクトリを表示します。|
|[Get-CcVersion](get-ccversion.md) <p> バージョン 2.0 以降|Cloud Connector インスタンスのバージョンを返します。 Get-CCVersionは、Cloud Connector のホスト マシンでのみ使用できます。|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> バージョン 2.0 以降|Skype for Business クラウド コネクタ エディション構成をローカル ファイルから Cloud Connector ホスト サーバーにインポートします。|
|[Install-CcAppliance](install-ccappliance.md)|ホスト サーバーにクラウド コネクタ アプライアンス (AD、Central Management Microsoft Store、仲介サーバー、エッジ サーバー仮想マシンなど) をインストールします。|
|[Publish-CcAppliance](publish-ccappliance.md)|オンライン テナント構成から高可用性情報を取得し、ホスト サーバー上の Cloud Connector アプライアンスに発行します。|
|[Register-CcAppliance](register-ccappliance.md)|オンライン テナント構成で、アプライアンス情報を PSTN サイトに登録します。 アプライアンスを Cloud Connector 管理サービスでデプロイおよび管理するには、事前にアプライアンスを登録する必要があります。|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> バージョン 1.4.2 以降|Cloud Connector のサイト共有ディレクトリの下にある CA フォルダー内の証明機関サービス バックアップ ファイル "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" を削除します。|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> バージョン 1.4.2 以降|Renew-CcCACertificateコマンドレットまたは更新 CcServerCertificate コマンドレットを実行した後、Central Management Microsoft Store、仲介サーバー、およびエッジ サーバー上のレガシ サーバー証明書を削除します。|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> バージョン 1.4.2 のみ|証明機関サービス AD Server を再インストールして、新しいルート CA 証明書を作成します。|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> バージョン 1.4.2 のみ|Cloud Connector の有効期限が近づいているか、既に有効期限が切れている場合に、Cloud Connector の証明書を更新します。|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> バージョン 1.4.2 以降|証明機関サーバーをリセットして、新しい証明機関証明書をインストールします。|
|[Restore-CcCredentials](restore-cccredentials.md) <p> バージョン 2.1 以降|資格情報をクリーンアップし、現在の Cloud Connector デプロイに使用されているすべての資格情報を再入力するように求められます。|
|[Search-CcLog](search-cclog.md)|Cloud Connector アプライアンスのログ ディレクトリで着信と発信の通話ログを検索します|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Cloud Connector ホスト サーバー上の作業ディレクトリを設定します。 すべてのデプロイ ファイルは、このディレクトリに格納されます。|
|[Set-CcCredential](set-cccredential.md)|現在の Cloud Connector デプロイの資格情報を設定します。|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|仲介サーバーまたはエッジ サーバーの証明書が格納されるパスを指定します。|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Cloud Connector のサイト レベルの構成ファイルを格納するディレクトリを設定します。 フォルダーには、ベース VHD と Cloud Connector の構成ファイルが含まれます。|
|[Start-CcDownload](start-ccdownload.md)|Cloud Connector ビットと msi ファイルを同期的にダウンロードします。|
|[Start-CcLogging](start-cclogging.md)|Cloud Connector アプライアンスの着信と発信の呼び出しログを生成します。|
|[Stop-CcLogging](stop-cclogging.md)|Cloud Connector アプライアンスの着信と発信の呼び出しログの生成を停止します。|
|[Switch-CcVersion](switch-ccversion.md)|実行中のアプライアンスを切断し、新しくデプロイされたアプライアンスまたはバックアップ アプライアンスに切り替えます。|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|実行中の Cloud Connector アプライアンスをホスト サーバーからアンインストールします。|
|[Unregister-CcAppliance](unregister-ccappliance.md)|オンライン テナント構成で PSTN サイトから現在の Cloud Connector アプライアンスの登録を解除します。|
|[Update-CcCACertificate](update-cccacertificate.md) <p> バージョン 2.0 以降|証明機関サービス AD Server を再インストールして、新しいルート CA 証明書を作成します。|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> バージョン 2.0 以降|Cloud Connector の有効期限が近づいているか、既に有効期限が切れている場合に、Cloud Connector の証明書を更新します。|
