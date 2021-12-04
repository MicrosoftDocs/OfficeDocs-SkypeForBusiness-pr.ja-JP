---
title: Microsoft Teams 会議室のセキュリティ
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 会議室デバイスをセキュリティで保護するMicrosoft Teams確認します。
ms.openlocfilehash: 7043b49406b0865ef38108519040374d792ac1dd
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306112"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 会議室のセキュリティ

Microsoft はパートナーと協力して、セキュリティで保護されたソリューションを提供し、会議室をセキュリティで保護するための追加のアクションMicrosoft Teamsします。 この記事では、Teams Rooms に含まれるセキュリティ機能の多くについて説明します。

> [!NOTE]
> Microsoft Teamsルームは、一般的なエンド ユーザー ワークステーションとして扱う必要があります。 使用例が大幅に異なるだけでなく、既定のセキュリティ プロファイルも大きく異なります。
> この記事は、Microsoft Teamsで実行されている会議室デバイスにWindows。

制限付きエンド ユーザー データは、Teamsされます。 エンド ユーザー データは、トラブルシューティングとサポートのみを行うログ ファイルに格納できます。 会議室を使用する会議の出席者は、Teamsファイルをハード ドライブにコピーしたり、自分でサインインしたりする必要はありません。 エンド ユーザー データは、会議室デバイスに転送またはアクセスMicrosoft Teamsはありません。

エンド ユーザーが会議室のハード ドライブにファイルTeamsすることはできませんが、Microsoft Defender は引き続き有効です。 Teams会議室のパフォーマンスは、Microsoft Defender でテストされます。 これを無効にするか、エンドポイント セキュリティ ソフトウェアを追加すると、予期しない結果が生じ、システムが低下する可能性があります。

## <a name="hardware-security"></a>ハードウェアのセキュリティ

Teams Rooms 環境には、このエディションで実行される中央のコンピューティング モジュールWindows 10 IoT Enterpriseがあります。 すべての認定コンピューティング モジュールには、セキュリティで保護されたマウント ソリューション、セキュリティ ロック スロット (例: 大きなロック)、承認されていないデバイスの接続を防ぐための I/O ポート アクセス セキュリティ対策が必要です。 統合拡張ファームウェア インターフェイス (UEFI) 構成を使用して、特定のポートを無効にすることもできます。

認定されたコンピューティング モジュールは、信頼できるプラットフォーム モジュール (TPM) 2.0 に準拠したテクノロジが既定で有効になっている必要があります。 TPM は、会議室リソース アカウントのログイン情報Teamsするために使用されます。

セキュリティで保護されたブートは既定で有効になっています。 セキュア ブートは、PC 業界のメンバーによって開発されたセキュリティ標準です。これは、OEM (Original Equipment Manufacturer) によって信頼されているソフトウェアのみを使用してデバイスを起動するために役立ちます。 PC が起動すると、ファームウェアは、UEFI ファームウェア ドライバー (Option ROM とも呼ばれる)、EFI アプリケーション、オペレーティング システムなど、ブート ソフトウェアの各部分の署名をチェックします。 署名が有効な場合は、PC が起動し、ファームウェアによってオペレーティング システムが制御されます。 詳細については、セキュア ブートに関 [するページを参照してください](/windows-hardware/design/device-experiences/oem-secure-boot)。

UEFI 設定へのアクセスは、物理キーボードとマウスを接続することでのみ可能です。 これにより、Teams Rooms タッチ対応本体と、Teams Rooms に接続されているその他のタッチ対応ディスプレイを介して UEFI にアクセスできません。

カーネル ダイレクト メモリ アクセス (DMA) 保護は、Windows 10 ルームで有効になっているTeams設定です。 この機能により、OS とシステム ファームウェアは、すべての DMA 対応デバイスに対する悪意のある意図しない DMA 攻撃からシステムを保護します。

- ブート プロセス中。

- OS の実行時に、M.2 PCIe スロットや Thunderbolt 3 など、簡単にアクセスできる内部/外部 DMA 対応ポートに接続されたデバイスによる悪意のある DMA に対して。

Teams Rooms では、ハイパーバイザーで保護されたコード整合性 (HVCI) も有効になります。 HVCI によって提供される機能の 1 つは Credential Guard です。 Credential Guard には、次の利点があります。

- **ハードウェアのセキュリティ** NTLM、Kerberos、Credential Manager は、Secure Boot や仮想化などのプラットフォーム セキュリティ機能を利用して資格情報を保護します。

- **仮想化ベースのセキュリティ Windows** NTLM および Kerberos の派生資格情報と他のシークレットは、実行中のオペレーティング システムから分離された保護された環境で実行されます。

- **高度な永続的な脅威に対する保護の強化** Credential Manager ドメインの資格情報、NTLM、Kerberos から派生した資格情報が仮想化ベースのセキュリティを使用して保護されている場合、多くのターゲット攻撃で使用される資格情報の盗難攻撃手法とツールはブロックされます。 管理特権を持つオペレーティング システムで実行されているマルウェアは、仮想化ベースのセキュリティによって保護されているシークレットを抽出できない。

## <a name="software-security"></a>ソフトウェア セキュリティ

Microsoft がWindowsすると、Teams Rooms は、Windows という名前のローカル ユーザー アカウントに自動的Skype。 アカウントSkypeパスワードはありません。 アカウント セッションSkypeセキュリティで保護するには、次の手順を実行します。

> [!IMPORTANT]
> パスワードを変更したり、ローカル ユーザー アカウントをSkypeしたりしない。 そうすることで、会議室Teams自動的にサインインするのを防ぐ可能性があります。

Microsoft Teams Rooms アプリは、1903 以降で見つかった割り当てアクセスWindows 10使用して実行されます。 割り当てられたアクセスは、Windows 10に公開されるアプリケーション エントリ ポイントを制限する機能です。 これは、シングル アプリ キオスク モードを有効にする方法です。 Shell 起動ツール をTeams、Windows デスクトップ アプリケーションをユーザー インターフェイスとして実行するキオスク デバイスとして構成されます。 Microsoft Teams Rooms アプリは、ユーザーがログオンするときに通常実行される既定のシェル (explorer.exe) を置き換えるアプリです。 言い換えると、従来のエクスプローラー シェルは起動されません。 これにより、Microsoft Teams 内の Microsoft Teams の脆弱性が大幅に軽減Windows。 詳細については、「デスクトップ エディションでキオスクとデジタル標識を構成[する」Windows参照してください](/windows/configuration/kiosk-methods)。

Teams Rooms でセキュリティ スキャンまたはインターネット セキュリティセンター (CIS) ベンチマークを実行する場合、Skype ユーザー アカウントでは Teams Rooms アプリ以外のアプリケーションの実行がサポートされていませんので、ローカル管理者アカウントのコンテキストでのみスキャンを実行できます。 Skype ユーザー コンテキストに適用されるセキュリティ機能の多くは、他のローカル ユーザーには適用されません。そのため、これらのセキュリティ スキャンでは、Skype アカウントに適用される完全なセキュリティ ロックダウンは表示されません。 そのため、Teams Rooms でローカル スキャンを実行Teamsされません。 ただし、必要に応じて外部侵入テストを実行できます。 この理由から、ローカル スキャンを実行する代わりに、Teams Rooms デバイスに対して外部侵入テストを実行することをお勧めします。

さらに、非管理機能の使用を制限するために、ロックダウン ポリシーが適用されます。 割り当て済みアクセス ポリシーの対象ではない、セキュリティで保護されていない可能性があるキーボードの組み合わせをインターセプトしてブロックするには、キーボード フィルターを有効にします。 ローカルまたはドメインの管理者権限を持つユーザーだけが、会議室を管理するためにWindowsにTeamsできます。 Windows Rooms デバイス上の Windows に適用されるこれらのポリシー Microsoft Teamsポリシーは、製品ライフサイクル中に継続的に評価およびテストされます。

## <a name="account-security"></a>アカウントのセキュリティ

Teams会議室デバイスには、"Admin" という名前の管理アカウントと既定のパスワードが含まれます。 セットアップが完了したら、できるだけ早く既定のパスワードを変更することを強く推奨します。

管理者アカウントは、会議室デバイスの適切な操作Teams必要ありません。名前を変更したり、削除したりすることもできます。 ただし、管理者アカウントを削除する前に、Teams Rooms デバイスに含むアカウントを削除する前に、構成された代替ローカル管理者アカウントを設定してください。 組み込みの Windows ツールまたは PowerShell を使用してローカル Windows Windows アカウントのパスワードを変更する方法の詳細については、次を参照してください。

- [パスワードを変更またはリセットWindowsする](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

ドメイン アカウントは、ローカルの管理者グループWindowsインポートすることもできます。 Intune を使用して、Azure ADアカウントに対してこれを行います。 詳細については、「Policy [CSP – RestrictedGroups」を参照してください](/windows/client-management/mdm/policy-csp-restrictedgroups)。

> [!NOTE]
> クリストロン コンソールを使用している場合は、本体とコンピューティング モジュールの管理パスワードも必ず更新してください。 詳細については、クレスロンにお問い合わせください。

> [!CAUTION]
> 別のローカル またはドメイン アカウントにローカル管理者アクセス許可を付与する前に管理者アカウントを削除または無効にすると、Teams Rooms デバイスを管理する機能が失われる可能性があります。 この場合は、デバイスを元の設定にリセットし、セットアップ プロセスを再度完了する必要があります。

ローカルユーザー アカウントにローカル管理者のアクセス許可Skype付与しない。

Windows構成デザイナーを使用して、プロビジョニング パッケージWindows 10作成できます。 ローカルの管理者パスワードの変更と共に、コンピューター名の変更や、コンピューター名への登録などAzure Active Directory。 構成デザイナーのプロビジョニング パッケージの作成のWindows、構成デザイナーのプロビジョニング パッケージに関する[ページをWindows 10。](/windows/configuration/provisioning-packages/provisioning-packages)

会議室デバイスにサインインするには、Teams デバイスごとにリソース アカウントを作成するTeams。 このアカウントで 2 要素認証または多要素認証を使用することはできません。 2 つ目の要素を要求すると、再起動後にアカウントが Teams Rooms アプリに自動的にサインインできない可能性があります。 ただし、このアカウントのセキュリティを強化するには、Modern Authentication を有効にできます。 さらに、リソース アカウントに対して場所ベースの条件付きアクセス ポリシーをデプロイして、未承認の場所からアカウントにサインインすることはできません。 詳細については、「条件付きアクセス [ポリシーでの場所の条件の使用」を参照してください。](/azure/active-directory/conditional-access/location-condition)

可能であれば、リソース アカウントを Azure ADすることをお勧めします。 同期されたアカウントは、ハイブリッド展開の Teams 会議室で動作しますが、これらの同期されたアカウントは多くの場合、Teams Rooms へのサインインに問題が発生し、トラブルシューティングが困難な場合があります。 サード パーティのフェデレーション サービスを使用してリソース アカウントの資格情報を認証する場合は、サード パーティ IDP が 属性を に設定して `wsTrustResponse` 応答します `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>ネットワーク セキュリティ

一般にTeams Rooms には、すべてのクライアントと同じネットワーク要件Microsoft Teamsがあります。 ファイアウォールや他のセキュリティ デバイスを介したアクセスは、他のTeamsクライアントの場合と同Microsoft Teamsです。 会議室にTeams、ユーザーの "必須" として表示されるカテゴリはTeamsファイアウォールで開く必要があります。 Teamsルームは、更新、Windows、Microsoft Intune Microsoft Store (Microsoft Intune を使用してデバイスを管理する場合) にアクセスする必要があります。 会議室に必要な IPS と URL の完全な一覧についてはMicrosoft Teams参照してください。

- **Microsoft Teams Office 365** [URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update Configure** [WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store**[と教育のビジネス向け Microsoft Store前提条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune**[ネットワーク エンドポイントのMicrosoft Intune](/mem/intune/fundamentals/intune-endpoints)

Microsoft Teams Rooms プレミアム の Microsoft Teams Rooms マネージド サービス コンポーネントを使用している場合は、Teams Rooms が次の URL にアクセスできる必要もあります。

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teamsルームは、セキュリティ更新プログラムを含む最新の更新プログラムWindows自動的に修正プログラムを適用するように構成されています。 Teamsは、事前に設定されたローカル ポリシーを使用して、毎日午前 2 時から保留中の更新プログラムをインストールします。 新しい更新プログラムをデプロイして適用するために追加のツールを使用Windowsはありません。 追加のツールを使用して更新プログラムをデプロイおよび適用すると、更新プログラムのインストールWindows、デプロイの安全性が低い可能性があります。 Teams Rooms アプリは、次のコマンドを使用してMicrosoft Store。 デバイスに Microsoft Teams Rooms Standard のライセンスが適用されている場合、夜間の修正プログラムの適用プロセス中に、アプリの新しいバージョンが自動的にインストールされます。 デバイスに Microsoft Teams Rooms プレミアム のライセンスが与え、Microsoft Managed Service に登録されている場合、定義済みのロールアウト 計画に基Teams Rooms アプリの新しいバージョンがインストールされます。

Teams Rooms デバイスは、ほとんどの 802.1X または他のネットワーク ベースのセキュリティ プロトコルで動作します。 ただし、可能性があるすべてのネットワーク セキュリティ構成Teams会議室をテストする機能は提供されています。 そのため、ネットワーク パフォーマンスの問題にトレースされる可能性があるパフォーマンスの問題が発生した場合は、組織でこれらのプロトコルが構成されている場合は、これらのプロトコルを無効にする必要があります。

リアルタイム メディアの最適なパフォーマンスを実現するには、プロキシ サーバーや他のネットワーク セキュリティ デバイスをバイパスTeamsメディア トラフィックを構成することを強く推奨します。 リアルタイム メディアは非常に待機時間が重要であり、プロキシ サーバーとネットワーク セキュリティ デバイスは、ユーザーのビデオとオーディオの品質を大幅に低下させる可能性があります。 また、Teamsは既に暗号化されています。プロキシ サーバー経由でトラフィックを渡すという具体的なメリットはありません。 詳細については、「ネットワークアップ[(クラウドへのネットワーク)](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) - Microsoft Teams 会議室と Microsoft Teams 会議室を使用してメディアのパフォーマンスを向上させるネットワークの推奨事項について説明する 1 つのアーキテクトの視点」を参照してください。

> [!IMPORTANT]
> Teamsは、認証済みプロキシ サーバーをサポートしません。

Teams会議室デバイスは、内部 LAN に接続する必要はない。 インターネットに直接アクセスTeamsセキュリティで保護されたネットワーク セグメントに会議室を配置します。 内部 LAN が侵害された場合、会議室に対する攻撃Teams機会が減少します。

会議室デバイスを有線ネットワークTeams接続することを強く推奨します。 Teams Rooms デバイスでのワイヤレス ネットワークの使用は推奨または認定されていません。 Wi-Fi Sense などの一部の接続機能は、既定で無効になっています。

近接結合と他の Teams ルーム機能は、Bluetooth。 ただし、Bluetooth Rooms Teamsの実装では、Teams Rooms デバイスへの外部デバイス接続は許可されません。 Bluetooth Rooms デバイスでのTeamsの使用は、現在、広告ビーコンとプロンプトされた近位接続に制限されています。 プロトコル `ADV_NONCONN_INT` データ ユニット (PDU) の種類は、広告ビーコンで使用されます。 この PDU の種類は、リッスンしているデバイスに情報を提供する接続できないデバイス向けです。 これらの機能のBluetoothデバイスのペアリングに関する情報はありません。 プロトコルの詳細Bluetooth SIG Web サイトを参照Bluetooth[参照してください](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
