---
title: Microsoft Teams Rooms セキュリティ
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
- Teams_ITAdmin_Rooms
description: Microsoft Teams Rooms デバイスをセキュリティで保護する方法について説明します。
ms.openlocfilehash: 231039324e15afb7b24f194623e54455d51e85c2
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606216"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams Rooms セキュリティ

Microsoft はパートナーと協力して、Microsoft Teams Rooms をセキュリティで保護するための追加のアクションを必要としない、セキュリティで保護されたソリューションを提供します。 この記事では、Teams Rooms にあるセキュリティ機能の多くについて説明します。

> [!NOTE]
> Microsoft Teams Rooms を一般的なエンドユーザー ワークステーションのように扱ってはなりません。 ユース ケースが大きく異なるだけでなく、既定のセキュリティ プロファイルも大きく異なります。
> この記事は、Windows で実行されている Microsoft Teams Rooms デバイスに適用されます。

制限付きエンドユーザー データは Teams Rooms に保存されます。 エンド ユーザー データは、トラブルシューティングとサポートのみを目的としてログ ファイルに格納される場合があります。 Teams Rooms を使用して会議の出席者がファイルをハード ドライブにコピーしたり、自分でサインインしたりすることは決してできません。 エンド ユーザー データが Microsoft Teams Rooms デバイスに転送されたり、Microsoft Teams Rooms デバイスからアクセスされたりすることはありません。

エンド ユーザーは Teams Rooms のハード ドライブにファイルを配置できませんが、Microsoft Defender は引き続き有効です。 Teams Rooms のパフォーマンスは Microsoft Defender でテストされます。 これを無効にするか、エンドポイント セキュリティ ソフトウェアを追加すると、予期しない結果が発生し、システム低下を招く可能性があります。

## <a name="hardware-security"></a>ハードウェアのセキュリティ

Teams Rooms 環境には、Windows 10 IoT Enterprise エディションを実行する中央コンピューティング モジュールがあります。 すべての認定コンピューティング モジュールには、承認されていないデバイスの接続を防ぐために、セキュリティで保護されたマウント ソリューション、セキュリティ ロック スロット (Kensington ロックなど)、およびI/O ポート アクセスのセキュリティ対策が必要です。 また、Unified Extensible Firmware Interface (UEFI) 構成を使用して特定のポートを無効にすることもできます。

すべての認定コンピューティング モジュールは、Trusted Platform Module (TPM) 2.0 準拠のテクノロジが既定で有効になった状態で出荷される必要があります。 TPM は、Teams Rooms リソース アカウントのログイン情報を暗号化するために使用されます。

セキュア ブートは既定で有効になっています。 セキュア ブートは、PC 業界のメンバーによって開発されたセキュリティ標準であり、OEM (Original Equipment Manufacturer) によって信頼されているソフトウェアのみを使用してデバイスが起動することを保証します。 PC が起動すると、ファームウェアは、UEFI ファームウェア ドライバー (オプション ROM とも呼ばれます)、EFI アプリケーション、オペレーティング システムなど、ブート ソフトウェアの各部分の署名を確認します。 署名が有効な場合は PC が起動し、ファームウェアによってオペレーティング システムに制御が与えられます。 詳細については「[セキュア ブート](/windows-hardware/design/device-experiences/oem-secure-boot)」を参照してください。

UEFI 設定へのアクセスは、物理キーボードとマウスを接続することによってのみ可能です。 これにより、Teams Rooms のタッチ対応コンソールや、Teams Rooms にアタッチされているその他のタッチ対応ディスプレイを介して UEFI にアクセスできなくなります。

カーネル直接メモリ アクセス (DMA) 保護は、Teams Rooms で有効になっている Windows 10 の設定です。 この機能により、OS とシステム ファームウェアは、すべての DMA 対応デバイスに対する悪意のある意図しない DMA 攻撃からシステムを保護します。

- ブート プロセス中。

- OS の実行時に、M.2 PCIe スロットや Thunderbolt 3 などの簡単にアクセスできる内部/外部 DMA 対応ポートに接続されたデバイスによる悪意のある DMA に対抗する。

Teams Rooms では、ハイパーバイザーで保護されたコード整合性 (HVCI) も有効になります。 HVCI によって提供される機能の 1 つとして Credential Guard があります。 Credential Guard には、次の利点があります:

- **ハードウェア セキュリティ** NTLM、Kerberos、資格情報マネージャーは、セキュア ブートや仮想化などのプラットフォーム セキュリティ機能を利用して資格情報を保護します。

- **仮想化ベースのセキュリティ** Windows NTLM および Kerberos 派生の資格情報およびその他のシークレットは、実行中のオペレーティング システムから分離された、保護された環境で実行されます。

- **高度な永続的な脅威に対する対策保護** 資格情報マネーカーのドメイン資格情報、NTLM、Kerberos 派生の資格情報を、仮想化ベースのセキュリティを使用して保護すると、多くの標的型攻撃で使用される資格情報盗難攻撃手法とツールをブロックできます。 管理者特権でオペレーティング システムで実行されているマルウェアは、仮想化ベースのセキュリティによって保護されているシークレットを抽出できません。

## <a name="software-security"></a>ソフトウェアのセキュリティ

Microsoft Windows の起動後、Teams Rooms は自動的に Skype という名前のローカル Windows ユーザー アカウントにサインインします。 Skype アカウントにパスワードがありません。 Skype アカウント セッションをセキュリティで保護するには、次の手順を実行します。

> [!IMPORTANT]
> パスワードを変更したり、ローカルの Skype ユーザー アカウントを編集したりしないでください。 そうすると、Teams Rooms が自動的にサインインできなくなる可能性があります。

Microsoft Teams Rooms アプリは、Windows 10 1903 以降で見つかった割り当てられたアクセス機能を使用して実行されます。 割り当てられたアクセスは、ユーザーに公開されるアプリケーション エントリ ポイントを制限する Windows 10 の機能です。 これにより、シングル アプリ キオスク モードが有効になります。 シェル ランチャーを使用して、Teams Rooms は、Windows デスクトップ アプリケーションをユーザー インターフェイスとして実行するキオスク デバイスとして構成されます。 Microsoft Teams Rooms アプリは、ユーザーがログオンしたときに通常実行される既定のシェル (explorer.exe) を置き換えます。 つまり、従来の Explorer シェルはまったく起動しません。 これにより、Windows 内の Microsoft Teams Rooms の脆弱性が大幅に軽減されます。 詳細については、「[Windows デスクトップ エディションでキオスクとデジタル署名を構成する](/windows/configuration/kiosk-methods)」を参照してください。

Teams Rooms でセキュリティ スキャンまたは Center for Internet Security (CIS) ベンチマークを実行する場合、Skype ユーザー アカウントは Teams Rooms アプリ以外のアプリケーションの実行をサポートしていないため、スキャンはローカル管理者アカウントのコンテキストでしか実行できません。 Skype ユーザー コンテキストに適用されるセキュリティ機能の多くは、他のローカル ユーザーには適用されません。その結果、これらのセキュリティ スキャンでは、Skype アカウントに適用される完全なセキュリティ ロックダウンは表示されません。 そうした理由から Teams Rooms でローカル スキャンを実行することはお勧めしません。 ただし、必要に応じて外部侵入テストを実行できます。 このため、ローカル スキャンを実行するのではなく、Teams Rooms デバイスに対して外部侵入テストを実行することをお勧めします。

さらに、管理以外の機能の使用を制限するために、ロックダウン ポリシーが適用されます。 割り当てられたアクセス ポリシーの対象になっていない、セキュリティで保護されていない可能性のあるキーボードの組み合わせを妨害してブロックするためにキーボード フィルターが有効になっています。 ローカルまたはドメインの管理者権限を持つユーザーのみが Teams Rooms を管理するために Windows にサインインできます。 Microsoft Teams Rooms デバイス上の Windows に適用されるこれらのポリシーおよびその他のポリシーは、製品ライフサイクル中に継続的に評価およびテストされます。

## <a name="account-security"></a>アカウントのセキュリティ

Teams Rooms デバイスには、既定のパスワード付きの "Admin" という名前の管理アカウントが含まれています。 セットアップが完了したら、できるだけ早く既定のパスワードを変更することを強くお勧めします。

管理者アカウントは、Teams Rooms デバイスを適切に操作するために必要ではなく、名前を変更することもできるし、削除しても構いません。 ただし、管理者アカウントを削除する前に、Teams Rooms デバイスの出荷時に付属するものを削除する前に、別のローカル管理者アカウントが構成されていることを確認してください。 組み込みの Windows ツールまたは PowerShell を使用してローカル Windows アカウントのパスワードを変更する方法の詳細については、次を参照してください:

- [Windows パスワードを変更またはリセットする](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

ドメイン アカウントをローカルの Windows 管理者グループにインポートすることもできます。 Intune を使用して、Azure AD アカウントに対してこれを行うことができます。 詳細については、「[ポリシー CSP – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups)」を参照してください。

> [!NOTE]
> Crestron コンソールをご使用の場合は、コンソールとコンピューティング モジュールの管理者パスワードも必ず更新してください。 詳細については、Crestron にお問い合わせください。

> [!CAUTION]
> 別のローカルまたはドメイン アカウントにローカル管理者アクセス許可を付与する前に管理者アカウントを削除または無効にすると、Teams Rooms デバイスを管理できなくなる可能性があります。 もしそうなってしまった場合は、デバイスを元の設定にリセットし、セットアップ プロセスをもう一度完了する必要があります。

Skype ユーザー アカウントにローカル管理者のアクセス許可を付与しないでください。

Windows 構成デザイナーを使用して、Windows 10 プロビジョニング パッケージを作成できます。 ローカル管理者パスワードの変更に加えて、コンピューター名の変更や Azure Active Directory への登録などを行うこともできます。 Windows 構成デザイナー プロビジョニング パッケージ作成の詳細については、「[Windows 10 のパッケージのプロビジョニングを行う方法](/windows/configuration/provisioning-packages/provisioning-packages)」を参照してください。

Teams にサインインできるように、Teams Rooms デバイスごとにリソース アカウントを作成する必要があります。 このアカウントでは、2 要素認証または多要素認証を使用できません。 2 つ目の要素を要求すると、再起動後にアカウントが Teams Rooms アプリに自動的にサインインできなくなります。 ただし、このアカウントのセキュリティを強化するために先進認証を有効にすることはできます。 さらに、Azure Active Directory 条件付きアクセス ポリシーとIntune コンプライアンス ポリシーをデプロイして、リソース アカウントをセキュリティで保護できます。 詳細については、「[Microsoft Teams Roomsおよび条件付きアクセスのサポートされる条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシー](supported-ca-and-compliance-policies.md)と[、Microsoft Teams Roomsの条件付きアクセスとIntuneコンプライアンス」を](conditional-access-and-compliance-for-devices.md)参照してください。

可能であれば、Azure AD でリソース アカウントを作成することをお勧めします。 同期されたアカウントはハイブリッド展開で Teams Rooms と連携できますが、同期されたアカウントでは Teams Rooms へのサインインが難しく、トラブルシューティングが困難になる可能性があります。 サード パーティのフェデレーション サービスを使用してリソース アカウントの資格情報を認証する場合は、サード パーティ IDP が `wsTrustResponse` 属性を `urn:oasis:names:tc:SAML:1.0:assertion` に設定して応答することを確認します。

## <a name="network-security"></a>ネットワーク セキュリティ

一般に、Teams Rooms には、Microsoft Teams クライアントと同じネットワーク要件があります。 ファイアウォールやその他のセキュリティ デバイス経由のアクセスは、他の Microsoft Teams クライアントの場合と同じです。 Teams Rooms に固有なものとしては、"required" として一覧表示されるカテゴリがファイアウォールで開かれている必要があります。 Teams Rooms では、Windows Update、Microsoft Store、Microsoft Intune へのアクセスも必要です (Microsoft Intune を使用してデバイスを管理する場合)。 Microsoft Teams Rooms に必要な IP と URL の完全なリストについては、以下をご覧ください:

- **Microsoft Teams** [Office 365 の URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [WSUS の構成](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [ビジネスおよび教育機関向け Microsoft Store の前提条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Microsoft Intune のネットワーク エンドポイント](/mem/intune/fundamentals/intune-endpoints)

Microsoft Teams Rooms Pro のMicrosoft Teams Roomsマネージド サービス コンポーネントを使用している場合は、Teams Roomsが次の URL にアクセスできることを確認する必要もあります。

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams Rooms は、セキュリティ更新プログラムを含む最新の Windows 更新プログラムで自動的に修正プログラムが適用されるように構成されています。 Teams Rooms では、事前に設定されたローカル ポリシーを使用して、毎日午前 2 時から保留中の更新プログラムがインストールされます。 Windows Update の展開と適用のために追加のツールを使用する必要はありません。 追加のツールを使用して更新プログラムを展開および適用すると、Windows 修正プログラムのインストールが遅れる可能性があるため、展開の安全性が低下します。 Teams Rooms アプリは、Microsoft Storeを使用して展開されます。

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

Teams Rooms デバイスは、ほとんどの 802.1X またはその他のネットワーク ベースのセキュリティ プロトコルで動作します。 ただし、考えられるすべてのネットワーク セキュリティ構成に対して Teams Rooms をテストすることはできません。 そのため、ネットワーク パフォーマンスの問題にトレースできるパフォーマンスの問題が発生した場合は、これらのプロトコルを無効にする必要があります (組織でこれらが構成されている場合)。

リアルタイム メディアの最適なパフォーマンスを得るには、プロキシ サーバーやその他のネットワーク セキュリティ デバイスをバイパスするように Teams メディア トラフィックを構成することを強くお勧めします。 リアルタイム メディアは待機時間にきわめて敏感であり、プロキシ サーバーとネットワーク セキュリティ デバイスにより、ユーザーのビデオとオーディオの品質が大幅に低下する可能性があります。 また、Teams メディアは既に暗号化されているため、プロキシ サーバー経由でトラフィックを渡すことによる具体的な利点はありません。 詳細については、「[ネットワーク アップ (クラウドへ) — あるアーキテクトの視点](/microsoft-365/solutions/networking-design-principles)」を参照してください。これには、Microsoft Teams と Microsoft Teams Rooms を使用してメディアのパフォーマンスを向上させるためのネットワークに関する推奨事項が説明されています。

> [!IMPORTANT]
> Teams Rooms では、認証されたプロキシ サーバーはサポートされていません。

Teams Rooms デバイスは、内部 LAN に接続する必要はありません。 インターネットに直接アクセスできるセキュリティで保護されたネットワーク セグメントに Teams Rooms を配置することを検討してください。 内部 LAN が侵害されると、Teams Rooms に対する攻撃ベクトルの機会が減少します。

Teams Rooms デバイスを有線ネットワークに接続することを強くお勧めします。 Teams Rooms デバイスでのワイヤレス ネットワークの使用は推奨も認定もされていません。 Wi-Fi Sense などの一部の接続機能は、既定で無効になっています。

近接通信参加やその他の Teams Rooms 機能は Bluetooth に依存しています。 ただし、Teams Rooms デバイスでの Bluetooth の実装では、Teams Rooms デバイスへの外部デバイス接続は許可されません。 Teams Rooms デバイスでの Bluetooth テクノロジの使用は、現在、ビーコンのアドバタイズとプロンプトされた近接接続に限定されています。 ビーコンのアドバタイズでは、`ADV_NONCONN_INT` プロトコル データ ユニット (PDU) 型が使用されます。 この PDU 型は、リッスンしているデバイスに情報をアドバタイズする非接続デバイス用です。 これらの機能の一部として、Bluetooth デバイスのペアリングはありません。 Bluetooth プロトコルの詳細については、[Bluetooth SIG Web サイト](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)を参照してください。
