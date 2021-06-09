---
title: Microsoft Teams ミーティングセキュリティ
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: デバイスをセキュリティで保護する方法Microsoft Teams ミーティングします。
ms.openlocfilehash: 24faadb4e139bdbddd8ed315faba7fd8c8257b83
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796701"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams ミーティングセキュリティ

Microsoft はパートナーと協力して、セキュリティで保護されたソリューションを提供し、セキュリティで保護するための追加のアクションを必要とMicrosoft Teams ミーティング。 この記事では、Teams ミーティング で見つかるセキュリティ機能の多くについて説明します。

> [!NOTE]
> Microsoft Teams ミーティング、一般的なエンド ユーザー ワークステーションのように扱う必要があります。 使用例が大幅に異なるだけでなく、既定のセキュリティ プロファイルも大きく異なります。
> この記事は、Microsoft Teams ミーティングで実行されているデバイスに適用Windows。

制限付きエンド ユーザー データは、Teams ミーティング。 エンド ユーザー データは、トラブルシューティングとサポートのみを行うログ ファイルに格納できます。 会議の出席者は、ファイルをハード ドライブTeams ミーティングコピーしたり、自分でサインインしたりする必要はありません。 エンド ユーザー データは、デバイスに転送またはアクセスMicrosoft Teams ミーティングされません。

エンド ユーザーがハード ドライブにファイルをTeams ミーティングすることはできませんが、Microsoft Defender は引き続き有効です。 Teams ミーティングは Microsoft Defender でテストされます。 これを無効にするか、エンドポイント セキュリティ ソフトウェアを追加すると、予期しない結果が生じ、システムが低下する可能性があります。

## <a name="hardware-security"></a>ハードウェアのセキュリティ

この環境Teams ミーティング、このエディションで実行される中央のコンピューティング モジュールWindows 10 IoT Enterpriseがあります。 すべての認定コンピューティング モジュールには、セキュリティで保護されたマウント ソリューション、セキュリティ ロック スロット (例: 大きなロック)、および承認されていないデバイスの接続を防ぐための I/O ポート アクセス セキュリティ対策が必要です。 統合拡張ファームウェア インターフェイス (UEFI) 構成を使用して、特定のポートを無効にすることもできます。

認定されたコンピューティング モジュールは、信頼できるプラットフォーム モジュール (TPM) 2.0 に準拠したテクノロジが既定で有効になっている必要があります。 TPM は、リソース アカウントのログイン情報を暗号化Teams ミーティング使用されます。

セキュリティで保護されたブートは既定で有効になっています。 セキュア ブートは、PC 業界のメンバーによって開発されたセキュリティ標準です。これは、OEM (Original Equipment Manufacturer) によって信頼されているソフトウェアのみを使用してデバイスを起動するために役立ちます。 PC が起動すると、ファームウェアは、UEFI ファームウェア ドライバー (Option ROM とも呼ばれる)、EFI アプリケーション、オペレーティング システムなど、ブート ソフトウェアの各部分の署名をチェックします。 署名が有効な場合は、PC が起動し、ファームウェアによってオペレーティング システムが制御されます。 詳細については、セキュア ブートに関 [するページを参照してください](/windows-hardware/design/device-experiences/oem-secure-boot)。

UEFI 設定へのアクセスは、物理キーボードとマウスを接続することでのみ可能です。 これにより、タッチ対応の本体Teams ミーティング、タッチ対応の他のディスプレイを介して UEFI にアクセスTeams ミーティング。

カーネル ダイレクト メモリ アクセス (DMA) 保護は、Windows 10で有効になっているTeams ミーティング。 この機能により、OS とシステム ファームウェアは、すべての DMA 対応デバイスに対する悪意のある意図しない DMA 攻撃からシステムを保護します。

- ブート プロセス中。

- OS の実行時に、M.2 PCIe スロットや Thunderbolt 3 など、簡単にアクセスできる内部/外部 DMA 対応ポートに接続されたデバイスによる悪意のある DMA に対して。

Teams ミーティングハイパーバイザーで保護されたコード整合性 (HVCI) も有効にします。 HVCI によって提供される機能の 1 つは Credential Guard です。 Credential Guard には、次の利点があります。

- **ハードウェアのセキュリティ** NTLM、Kerberos、Credential Manager は、Secure Boot や仮想化などのプラットフォーム セキュリティ機能を利用して資格情報を保護します。

- **仮想化ベースのセキュリティ Windows** NTLM および Kerberos の派生資格情報と他のシークレットは、実行中のオペレーティング システムから分離された保護された環境で実行されます。

- **高度な永続的な脅威に対する保護の強化** Credential Manager ドメインの資格情報、NTLM、Kerberos から派生した資格情報が仮想化ベースのセキュリティを使用して保護されている場合、多くのターゲット攻撃で使用される資格情報の盗難攻撃手法とツールはブロックされます。 管理特権を持つオペレーティング システムで実行されているマルウェアは、仮想化ベースのセキュリティによって保護されているシークレットを抽出できない。

## <a name="software-security"></a>ソフトウェア セキュリティ

Microsoft がWindowsすると、Teams ミーティング という名前のローカル ユーザー アカウントWindows自動的にサインインSkype。 アカウントSkypeパスワードはありません。 アカウント セッションSkypeセキュリティで保護するには、次の手順を実行します。

> [!IMPORTANT]
> パスワードを変更したり、ローカル ユーザー アカウントをSkypeしたりしない。 そうすることで、ユーザー Teams ミーティングサインインを防ぐ可能性があります。

1903 Microsoft Teams ミーティング 1903 以降の割り当て済みアクセス機能を使用Windows 10アプリが実行されます。 割り当てられたアクセスは、Windows 10に公開されるアプリケーション エントリ ポイントを制限する機能です。 これは、シングル アプリ キオスク モードを有効にする方法です。 Shell 起動ツールをTeams ミーティング、デスクトップ アプリケーションをユーザー インターフェイスとして実行Windowsキオスク デバイスとして構成されます。 ユーザー Microsoft Teams ミーティングログオン時に通常実行される既定のシェル (explorer.exe) は、アプリによって置き換えてください。 言い換えると、従来のエクスプローラー シェルは起動されません。 これにより、アプリケーション内のMicrosoft Teams ミーティングの脆弱性が大幅にWindows。 詳細については、「デスクトップ エディションでキオスクとデジタル標識を構成[するWindows参照してください](/windows/configuration/kiosk-methods)。

Teams ミーティング でセキュリティ スキャンまたはインターネット セキュリティセンター (CIS) ベンチマークを実行する場合、Skype ユーザー アカウントでは Teams ミーティング アプリ以外のアプリケーションの実行がサポートされていませんので、ローカル管理者アカウントのコンテキストでのみスキャンを実行できます。 Skype ユーザー コンテキストに適用されるセキュリティ機能の多くは、他のローカル ユーザーには適用されません。そのため、これらのセキュリティ スキャンでは、Skype アカウントに適用される完全なセキュリティ ロックダウンは表示されません。 そのため、ローカル ネットワークでローカル スキャンを実行Teams ミーティング。 ただし、必要に応じて外部侵入テストを実行できます。 この理由から、ローカル スキャンを実行する代わりに、Teams ミーティング デバイスに対して外部侵入テストを実行することをお勧めします。

さらに、非管理機能の使用を制限するために、ロックダウン ポリシーが適用されます。 割り当て済みアクセス ポリシーの対象ではない、セキュリティで保護されていない可能性があるキーボードの組み合わせをインターセプトしてブロックするには、キーボード フィルターを有効にします。 ローカルまたはドメインの管理者権限を持つユーザーだけが、管理者アカウントにサインインしてWindowsを管理Teams ミーティング。 これらのポリシーと、デバイス上の Windowsに適用Microsoft Teams ミーティングポリシーは、製品のライフサイクル中に継続的に評価およびテストされます。

## <a name="account-security"></a>アカウントのセキュリティ

Teams ミーティングには、"Admin" という名前の管理アカウントと既定のパスワードが含まれます。 セットアップが完了したら、できるだけ早く既定のパスワードを変更することを強く推奨します。

管理者アカウントは、デバイスを適切に操作するために必要Teams ミーティング名前を変更したり、削除したりすることもできます。 ただし、管理者アカウントを削除する前に、Teams ミーティング デバイスに含むアカウントを削除する前に、構成された代替ローカル管理者アカウントを設定してください。 組み込みの Windows ツールまたは PowerShell を使用してローカル Windows Windows アカウントのパスワードを変更する方法の詳細については、次を参照してください。

- [パスワードを変更またはリセットWindowsする](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

ドメイン アカウントは、ローカルの管理者グループWindowsインポートすることもできます。 これは、Intune を使用して Azure ADアカウントに対して行います。 詳細については、「Policy [CSP – RestrictedGroups」を参照してください](/windows/client-management/mdm/policy-csp-restrictedgroups)。

> [!CAUTION]
> 別のローカル またはドメイン アカウントにローカル管理者アクセス許可を付与する前に管理者アカウントを削除または無効にすると、デバイスを管理Teams ミーティングがあります。 この場合は、デバイスを元の設定にリセットし、セットアップ プロセスを再度完了する必要があります。
>
> ローカルユーザー アカウントにローカル管理者のアクセス許可Skype付与しない。

Windows構成デザイナーを使用して、プロビジョニング パッケージWindows 10作成できます。 ローカルの管理者パスワードの変更と共に、コンピューター名の変更や、コンピューター名への登録などAzure Active Directory。 構成デザイナーのプロビジョニング パッケージの作成のWindows、構成デザイナーのプロビジョニング パッケージに関する[ページをWindows 10。](/windows/configuration/provisioning-packages/provisioning-packages)

デバイスにサインインするには、デバイスごとにリソース Teams ミーティング作成する必要Teams。 このアカウントで 2 要素認証または多要素認証を使用することはできません。 2 つ目の要素を必要とすると、再起動後にアカウントが Teams ミーティングにサインインできません。 ただし、このアカウントのセキュリティを強化するには、Modern Authentication を有効にできます。 さらに、リソース アカウントに対して場所ベースの条件付きアクセス ポリシーをデプロイして、未承認の場所からアカウントにサインインすることはできません。 詳細については、「条件付きアクセス [ポリシーでの場所の条件の使用」を参照してください。](/azure/active-directory/conditional-access/location-condition)

可能であれば、Azure リソース アカウントを Azure ADすることをお勧めします。 同期されたアカウントはハイブリッドデプロイの Teams ミーティング で動作しますが、これらの同期されたアカウントは多くの場合、Teams ミーティング へのサインインが困難であり、トラブルシューティングが難しい場合があります。 サード パーティのフェデレーション サービスを使用してリソース アカウントの資格情報を認証する場合は、サード パーティ IDP が 属性を に設定して `wsTrustResponse` 応答します `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>ネットワーク セキュリティ

一般にTeams ミーティングクライアントと同じネットワーク要件Microsoft Teamsがあります。 ファイアウォールや他のセキュリティ デバイスを介したアクセスは、他Teams ミーティングクライアントの場合と同Microsoft Teamsです。 [Teams ミーティングに固有のカテゴリは、ファイアウォールで開Teams"必須" と表示されている必要があります。 Teams ミーティング Update Windows、Microsoft Store、Microsoft Intune (Microsoft Intune を使用してデバイスを管理する場合) にアクセスする必要があります。 アプリケーションに必要な IPS と URL の完全な一覧についてはMicrosoft Teams ミーティング参照してください。

- **Microsoft Teams Office 365** [URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows更新プログラムの**[構成 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store**[と教育のビジネス向け Microsoft Store前提条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune**[のネットワーク エンポイントMicrosoft Intune](/mem/intune/fundamentals/intune-endpoints)

Microsoft Teams ミーティング プレミアム の Microsoft Teams ミーティング マネージド サービス コンポーネントを使用している場合は、Teams ミーティング が次の URL にアクセスできる必要もあります。

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

Teams ミーティング、セキュリティ更新プログラムを含む最新の更新プログラムに自動的Windows適用するように構成されています。 Teams ミーティングローカル ポリシーを使用して、毎日午前 2 時から保留中の更新プログラムをインストールします。 新しい更新プログラムをデプロイして適用するために追加のツールを使用Windowsはありません。 追加のツールを使用して更新プログラムをデプロイおよび適用すると、更新プログラムのインストールが遅Windows、デプロイの安全性が低い場合があります。 アプリTeams ミーティングは、次のコマンドを使用してMicrosoft Store。 デバイスが Microsoft Teams ミーティング Standard でライセンスされている場合、夜間の修正プログラムの適用プロセス中に、アプリの新しいバージョンが自動的にインストールされます。 デバイスに Microsoft Teams ミーティング プレミアム のライセンスが与え、Microsoft マネージド サービスに登録されている場合は、定義済みのロールアウト計画に基Teams ミーティング アプリの新しいバージョンがインストールされます。

Teams ミーティングデバイスは、ほとんどの 802.1X または他のネットワーク ベースのセキュリティ プロトコルで動作します。 ただし、考えられるすべてのネットワーク セキュリティ構成Teams ミーティングをテストするわけではありません。 そのため、ネットワーク パフォーマンスの問題にトレースできるパフォーマンスの問題が発生した場合は、組織でこれらのプロトコルが構成されている場合は、これらのプロトコルを無効にする必要があります。

リアルタイム メディアの最適なパフォーマンスを実現するには、プロキシ サーバーや他のネットワーク セキュリティ デバイスをバイパスTeamsメディア トラフィックを構成することを強く推奨します。 リアルタイム メディアは非常に待機時間が重要であり、プロキシ サーバーとネットワーク セキュリティ デバイスは、ユーザーのビデオとオーディオの品質を大幅に低下させる可能性があります。 また、Teamsは既に暗号化されています。プロキシ サーバー経由でトラフィックを渡すという具体的なメリットはありません。 詳細については、「(クラウドへの[)](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide)ネットワーク - Microsoft Teams と Microsoft Teams ミーティング でメディアのパフォーマンスを向上させるネットワークの推奨事項について説明する 1 人のアーキテクトの視点」を参照してください。

> [!IMPORTANT]
> Teams ミーティングプロキシ サーバーはサポートされていません。

Teams ミーティングデバイスは、内部 LAN に接続する必要があります。 インターネットに直接アクセスTeams ミーティングセキュリティで保護されたネットワーク セグメントに配置する方法を検討してください。 内部 LAN が侵害された場合、攻撃ベクトルの攻撃Teams ミーティング減ります。

デバイスを有線ネットワークに接続Teams ミーティングを強く推奨します。 デバイスでのワイヤレス ネットワークTeams ミーティング推奨または認定されていません。 Wi-Fi Sense などの一部の接続機能は、既定で無効になっています。

近接結合と他のTeams ミーティング機能は、Bluetooth。 ただし、BluetoothデバイスTeams ミーティング実装では、デバイスへの外部デバイス接続Teams ミーティングされません。 BluetoothデバイスでのTeams ミーティングの使用は、現在、ビーコンの広告とプロンプトの近位接続に制限されています。 プロトコル `ADV_NONCONN_INT` データ ユニット (PDU) の種類は、広告ビーコンで使用されます。 この PDU の種類は、リッスンしているデバイスに情報を提供する接続できないデバイス向けです。 これらの機能のBluetoothデバイスのペアリングに関する情報はありません。 プロトコルの詳細Bluetooth SIG Web サイトを参照Bluetooth[参照してください](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
