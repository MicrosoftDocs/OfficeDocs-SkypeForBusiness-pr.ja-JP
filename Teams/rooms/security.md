---
title: Microsoft Teams の会議室のセキュリティ
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
description: Microsoft Teams Rooms デバイスをセキュリティで保護する方法について説明します。
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880881"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams の会議室のセキュリティ

Microsoft はパートナーと協力して、セキュリティで保護されたソリューションを提供し、Microsoft Teams Rooms をセキュリティで保護するために追加のアクションを必要としない。 この記事では、Teams Rooms のセキュリティ機能の多くについて説明します。

> [!NOTE]
> Microsoft Teams の会議室は、一般的なエンド ユーザー ワークステーションと同様に扱う必要があります。 使用例が大幅に異なるだけでなく、既定のセキュリティ プロファイルも大幅に異なります。

制限されたエンド ユーザー データは、Teams の会議室に保存されます。 エンドユーザー データは、トラブルシューティングとサポートのみを行うログ ファイルに保存される場合があります。 Teams Rooms を使用する会議の出席者は、ファイルをハード ドライブにコピーしたり、自分自身でサインインしたりする必要はありません。 Microsoft Teams Rooms デバイスにエンドユーザー データを転送したり、アクセスしたりする必要はありません。

エンド ユーザーが Teams Rooms のハード ドライブにファイルを保存することはできませんが、Microsoft Defender は引き続き有効です。 Teams Rooms のパフォーマンスは Microsoft Defender でテストされます。 これを無効にするか、エンドポイント セキュリティ ソフトウェアを追加すると、予期しない結果が生じ、システムが低下する可能性があります。

## <a name="hardware-security"></a>ハードウェアのセキュリティ

Teams Rooms 環境には、Windows 10 IoT Enterprise エディションを実行する中央演算モジュールがあります。 認証済みのすべての計算モジュールには、セキュリティで保護されたマウント ソリューション、セキュリティ ロック スロット (例: インカリスト ロック)、および I/O ポート アクセスのセキュリティ対策が必要です。不正なデバイスの接続を防止します。 また、統合拡張ファームウェア インターフェイス ( EAP) 構成を使用して特定のポートを無効にすることもできます。

認定済みのすべての計算モジュールは、既定で有効になっているトラステッド プラットフォーム モジュール (TP) 2.0 準拠テクノロジと一緒に出荷する必要があります。 TPM は、Teams Rooms リソース アカウントのログイン情報を暗号化するために使用されます。

セキュリティで保護されたブートは既定で有効になっています。 セキュア ブートは、元の機器製造元 (OEM) によって信頼されているソフトウェアのみを使用してデバイスを起動するために PC 業界のメンバーによって開発されたセキュリティ標準です。 PC が起動すると、ファームウェアは、(Option ROM とも呼ばれる)、EFI アプリケーション、オペレーティング システムなどのブート ソフトウェアの各部分の署名をチェックします。 署名が有効な場合は、PC が起動し、ファームウェアによってオペレーティング システムが制御されます。 詳細については、「セキュア ブート」 [を参照してください](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。

KEYBOARD 設定へのアクセスは、物理キーボードとマウスを接続することでのみ可能です。 これにより、Teams Rooms タッチ対応コンソールおよび Teams 会議室に接続されているその他のタッチ対応ディスプレイを介して それ以外の ED にアクセスすることを防止します。

カーネル ダイレクト メモリ アクセス (DMA) 保護は、Teams の会議室で有効になっている Windows 10 の設定です。 この機能により、OS とシステムファームウェアは、DMA 対応のすべてのデバイスに対する悪意のある、意図しない DMA 攻撃からシステムを保護します。

- 起動プロセス中。

- OS 実行時に M.2 PCIe スロットや Thunderbolt 3 などの簡単にアクセス可能な内部/外部 DMA 対応ポートに接続されたデバイスによる悪意のある DMA に対して。

Teams の会議室では、HVC (分取り込み機能) によって保護されたコード整合性も有効になります。 HVCI によって提供される機能の 1 つは Credential Guard です。 Credential Guard には、次の利点があります。

- **ハードウェアのセキュリティ** NTLM、Kerberos、資格情報マネージャーは、Secure Boot や仮想化などのプラットフォームセキュリティ機能を利用して、資格情報を保護します。

- **仮想化ベースのセキュリティ** Windows NTLM と Kerberos の派生資格情報と他のシークレットは、実行中のオペレーティング システムから分離された保護された環境で実行されます。

- **高度な永続的な脅威に対する保護を強化する** 資格情報マネージャーのドメイン資格情報、NTLM、Kerberos 派生資格情報が仮想化ベースのセキュリティを使用して保護されている場合、多くの対象指定攻撃で使用される資格情報の盗難攻撃の手法とツールはブロックされます。 管理者権限を持つオペレーティング システムで実行されているマルウェアは、仮想化ベースのセキュリティによって保護されている秘密を抽出できない。

## <a name="software-security"></a>ソフトウェア セキュリティ

Microsoft Windows の起動後、Teams Rooms は Skype という名前のローカルの Windows ユーザー アカウントに自動的にサインインします。 Skype アカウントにはパスワードはありません。 Skype アカウント セッションをセキュリティで保護するには、次の手順を実行します。

> [!IMPORTANT]
> パスワードを変更したり、ローカルの Skype ユーザー アカウントを編集したりしない。 これにより、Teams の会議室が自動的にサインインしなからすのを防ぐ可能性があります。

Microsoft Teams Rooms アプリは、Windows 10 1903 以降の割り当て済みアクセス機能を使用して実行されます。 割り当てられた Access は、ユーザーに公開されるアプリケーション エントリ ポイントを制限する Windows 10 の機能です。 これは、単一アプリ キオスク モードを有効にする機能です。 Shell 起動ツールを使用して、Teams Rooms はユーザー インターフェイスとして Windows デスクトップ アプリケーションを実行するキオスク デバイスとして構成されます。 Microsoft Teams Rooms アプリは、ユーザーがログオンするときに通常実行される既定のシェル (explorer.exe) を置き換える機能です。 つまり、従来のエクスプローラー シェルは起動されません。 これにより、Windows 内の Microsoft Teams Rooms の脆弱性が大幅に軽減されます。 詳細については、「Windows デスクトップ エディション [でキオスクとデジタル署名を構成する」を参照してください](https://docs.microsoft.com/windows/configuration/kiosk-methods)。

Teams Rooms でセキュリティ スキャンまたはインターネット セキュリティセンター (CIR) のベンチマークを実行する場合は、Skype ユーザー アカウントが Teams Rooms アプリ以外のアプリケーションの実行をサポートしなわないので、スキャンはローカル管理者アカウントのコンテキストでのみ実行できます。 Skype ユーザー コンテキストに適用されるセキュリティ機能の多くは、他のローカル ユーザーには適用されません。そのため、これらのセキュリティ スキャンでは、Skype アカウントに適用される完全なセキュリティ ロックダウンは表示されません。 そのため、Teams の会議室でローカル スキャンを実行する方法は推奨されません。 ただし、必要に応じて外部侵入テストを実行できます。 この理由から、ローカル スキャンを実行する代わりに、Teams Rooms デバイスに対して外部侵入テストを実行することをお勧めします。

さらに、非管理機能の使用を制限するために、ポリシーのロックダウンが適用されます。 割り当て済み Access ポリシーの対象ではない、安全でない可能性があるキーボードの組み合わせを傍受およびブロックするには、キーボード フィルターが有効になります。 ローカルまたはドメインの管理者権限を持つユーザーだけが、Teams ルームを管理するために Windows にサインインできます。 Microsoft Teams Rooms デバイス上の Windows に適用されるこれらのポリシーおよび他のポリシーは、製品ライフサイクルの間、継続的に評価およびテストされます。

## <a name="account-security"></a>アカウントのセキュリティ

Teams 会議室デバイスには、"管理者" という名前の管理アカウントと既定のパスワードが含まれます。 セットアップが完了したら、できるだけ早く既定のパスワードを変更することを強く推奨します。

Teams Rooms デバイスを適切に操作するために管理者アカウントは必要ありません。名前を変更したり、削除したりすることもできます。 ただし、管理者アカウントを削除する前に、Teams Rooms デバイスに組み込みのアカウントを削除する前に、別のローカル管理者アカウントを設定してください。 組み込みの Windows ツールまたは PowerShell を使用してローカルの Windows アカウントのパスワードを変更する方法の詳細については、次を参照してください。

- [Windows パスワードを変更またはリセットする](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

ローカルの Windows 管理者グループにドメイン アカウントをインポートすることもできます。 Intune を使用して、Azure ADアカウントに対してこれを行います。 詳細については、「Policy [CSP – RestrictedGroups」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)。

> [!CAUTION]
> 別のローカル またはドメイン アカウントにローカル管理者権限を付与する前に管理者アカウントを削除または無効にすると、Teams Rooms デバイスを管理する機能が失われる可能性があります。 この場合は、デバイスを元の設定にリセットし、セットアップ プロセスを再度完了する必要があります。
>
> Skype ユーザー アカウントにローカルの管理者権限を付与しない。

Windows 構成デザイナーを使用して、Windows 10 プロビジョニング パッケージを作成できます。 ローカルの管理者パスワードの変更と共に、コンピューター名の変更や Azure Active Directory への登録なども行います。 Windows 構成デザイナープロビジョニング パッケージの作成の詳細については [、「Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)のプロビジョニング パッケージ」を参照してください。

Teams にサインインするには、Teams 会議室デバイスごとにリソース アカウントを作成する必要があります。 このアカウントでは、2 要素認証または多要素認証を使用することはできません。 2 つ目の要因を必要とすると、再起動後にアカウントが Teams Rooms アプリに自動的にサインインできない場合があります。 ただし、このアカウントのセキュリティを強化するには、最新の認証を有効にできます。 さらに、リソース アカウントに対して場所に基づく条件付きアクセス ポリシーを展開して、割り当てされていない場所からアカウントにサインインするのを防ぐ方法もあります。 詳細については、「条件付き [アクセス ポリシーでの場所の条件の使用」を参照してください。](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

可能であれば、Azure AD作成することをお勧めします。 同期されたアカウントは、ハイブリッド展開で Teams Rooms と動作しますが、これらの同期されたアカウントは、多くの場合、Teams の会議室へのサインインに問題を持ち、トラブルシューティングが難しい場合があります。 サードパーティ フェデレーション サービスを使用してリソース アカウントの資格情報を認証する場合は、サード パーティ IDP が属性を設定して応答します `wsTrustResponse` `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>ネットワーク セキュリティ

一般に、Teams Rooms には、Microsoft Teams クライアントと同じネットワーク要件があります。 ファイアウォールや他のセキュリティ デバイスを介したアクセスは、Teams 会議室の場合、他の Microsoft Teams クライアントの場合と同じです。 Teams ルームに固有の、Teams の "必須" として表示されるカテゴリは、ファイアウォールで開く必要があります。 Teams 会議室には、Windows Update、Microsoft Store、Microsoft Intune (デバイスの管理に Microsoft Intune を使用している場合) へのアクセスも必要です。 Microsoft Teams の会議室に必要な IP と URL の完全な一覧については、次を参照してください。

- **Microsoft Teams Office** [365 の URL と IP アドレス範囲を使用する](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update で** [WSUS を構成する](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **ビジネスおよび**[教育向け Microsoft Store の Microsoft Store の前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Network Enpoints for Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Microsoft Teams Rooms Premium の Microsoft Teams Rooms 管理サービス コンポーネントを使用している場合は、Teams 会議室が次の URL にアクセスできる必要もあります。

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

Teams Rooms は、セキュリティ更新プログラムを含む最新の Windows 更新プログラムに自動的にパッチを適用するように構成されています。 Teams Rooms は、事前に設定されたローカル ポリシーを使用して、毎日午前 2 時から保留中の更新プログラムをインストールします。 追加のツールを使用して Windows 更新プログラムを展開および適用する必要はありません。 追加のツールを使用して更新プログラムを展開および適用すると、Windows パッチのインストールが遅れて、展開の安全性が低い可能性があります。 Teams Rooms アプリは、Microsoft Store を使用して展開されます。 デバイスに Microsoft Teams Rooms Standard のライセンスが適用されている場合、夜間のパッチ適用プロセス中に、すべての新しいバージョンのアプリが自動的にインストールされます。 デバイスに Microsoft Teams Rooms Premium のライセンスが与え、Microsoft Managed Service に登録されている場合、新しいバージョンの Teams Rooms アプリは、定義されたロールアウトプランごとにインストールされます。

Teams Rooms デバイスは、ほとんどの 802.1X または他のネットワーク ベースのセキュリティ プロトコルで動作します。 ただし、可能性があるすべてのネットワーク セキュリティ構成に対して Teams Rooms をテストできるわけではありません。 そのため、ネットワーク パフォーマンスの問題をトレースできるパフォーマンスの問題が発生した場合は、組織でこれらのプロトコルが構成されている場合は無効にする必要があります。

リアルタイム メディアの最適なパフォーマンスを得る場合は、プロキシ サーバーや他のネットワーク セキュリティ デバイスをバイパスする Teams メディア トラフィックを構成することを強く推奨します。 リアルタイム メディアは待機時間が非常に高く、プロキシ サーバーとネットワーク セキュリティ デバイスは、ユーザーのビデオと音声の品質を大幅に低下させる可能性があります。 また、Teams メディアは既に暗号化されていますので、プロキシ サーバーを経由してトラフィックを通過するメリットはありません。 詳細については [、「Networking up (クラウドへ)](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) — Microsoft Teams および Microsoft Teams Rooms を使用してメディアのパフォーマンスを向上させるネットワーク推奨事項について説明する 1 人の設計者の力である」を参照してください。

> [!IMPORTANT]
> Teams 会議室は、認証されたプロキシ サーバーをサポートしません。

Teams Rooms デバイスは内部 LAN に接続する必要があります。 直接インターネットにアクセスできるセキュリティで保護されたネットワーク セグメントに Teams Rooms を配置します。 内部 LAN が侵害された場合、Teams Rooms に対する攻撃ベクターの機会は削減されます。

Teams Rooms デバイスを有線ネットワークに接続することを強く推奨します。 Teams Rooms デバイスでのワイヤレス ネットワークの使用は推奨または認定されていません。 Wi-Fi Sense などの一部の接続機能は、既定で無効になっています。

近接参加と他の Teams 会議室の機能は、Bluetooth。 ただし、Teams Rooms Bluetooth実装を行う場合、Teams Rooms デバイスへの外部デバイス接続は許可されません。 Bluetooth Teams Rooms デバイスでのテクノロジの使用は、現在、広告ビーコンと近位接続の要求に制限されています。 プロトコル `ADV_NONCONN_INT` データユニット (PDU) の種類は、広告ビーコンで使用されます。 この PDU の種類は、聞き取りデバイスに情報を提供する接続不可のデバイス用です。 これらの機能Bluetoothデバイスのペアリングに問題はありません。 このプロトコルのBluetoothは、SIG Web サイトBluetooth [参照してください](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
