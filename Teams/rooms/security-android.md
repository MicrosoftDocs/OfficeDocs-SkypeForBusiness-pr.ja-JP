---
title: Microsoft Teams for Android セキュリティ
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
description: Microsoft Teams for Android デバイスをセキュリティで保護する方法について説明します。
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532437"
---
# <a name="microsoft-teams-for-android-security"></a>Microsoft Teams for Android セキュリティ

この記事では、Microsoft エンドポイント マネージャーによって専用デバイス モード用に構成された Android デバイスについては説明しません。 Teams Android デバイスは、設計上キオスク モードで実行されます。 Android キオスクの詳細については、「 [Android Enterprise 専用デバイスの登録](/mem/intune/enrollment/android-kiosk-enroll)」を参照してください。

Microsoft は OEM パートナーと協力して、設計によってセキュリティで保護され、顧客のニーズに合わせてカスタマイズ可能なソリューションを提供しています。 この記事では、Teams Android デバイスに含まれるセキュリティ機能の多くとアプローチについて説明します。 ナビゲーションを容易にするために、4 つの主要なセクションに分割されています。

> [!NOTE]
> Microsoft Teams Android デバイスは、一般的な Android デバイスとして扱われるべきではありません。 Teams Android デバイスは、Teams とそれぞれのユース ケースで使用できるように設計された専用アプライアンスです。 この記事は、Android オペレーティング システムを実行している認定済み専用の Microsoft Teams デバイスにのみ適用されます。 Teams 認定デバイスは、認定 OEM ベンダーからのみ購入できます。 Microsoft Teams 認定 Android デバイスの詳細については、「 [Microsoft Teams 認定 Android デバイス」を](/microsoftteams/devices/teams-ip-phones)参照してください。

Windows デバイスのTeams Roomsのセキュリティの詳細については、「Windows [セキュリティのMicrosoft Teams Rooms」を](security-windows.md)参照してください。

## <a name="software-security"></a>ソフトウェア のセキュリティ

### <a name="android-kiosk-mode"></a>Android キオスク モード

Teams Android デバイスは、Android キオスク モードでデバイスを実行することで、承認されたアプリケーションのみを実行するためにロックダウンされます。 キオスク モードでは、ランチャー機能へのアクセスが無効になり、承認されたアプリケーションがデバイスで起動するようにデバイスをセキュリティで保護するのに役立ちます。  

| Application Name            | アプリケーションの説明                   |
|-----------------------------|-------------------------------------------|
| Microsoft Teams Android アプリ | Microsoft Teams デバイス アプリケーション        |
| Microsoft Teams 管理 エージェント | Teams 管理センターのリモート管理      |
| Intune ポータル サイト       | デバイス登録、登録&サインイン |
| OEM パートナー エージェント           | OEM パートナー エージェント & デバイス設定アプリ   |

設計上、Microsoft Teams Android アプリは Android キオスク モードで起動時に起動し、オペレーティング システムへのアクセスや、指定された Teams ユーザー エクスペリエンス以外のコンポーネントへのアクセスはユーザーに提供しません。

### <a name="application-code-signing"></a>アプリケーション コード署名

Microsoft アプリケーションと OEM アプリケーションはすべてコード署名済みです。 コード署名は、デバイス上で実行されているソフトウェアが Microsoft および Microsoft のハードウェア パートナーから正規のソフトウェアであることを検証する際に役立ちます。 また、コード署名は、正規のソフトウェアのみが起動および実行できるように、デバイスで実行されているソフトウェアの整合性を検証しようとします。  

### <a name="third-party-applications"></a>サード パーティ製アプリケーション

Teams 認定デバイスには、Google Play ストア、Amazon App Store、Google Play Services は設計上インストールされていません。 これにより、ストアからデバイスにサード パーティ製アプリケーションをインストールできないようにすることができます。  

### <a name="android-debug-bridge"></a>Android デバッグ ブリッジ

Android デバッグ ブリッジ (ADB) は、リリース ソフトウェアを実行しているすべての Teams Android デバイスで設計上無効になっています。 ADB は、管理者が Android ベースのデバイスで機能を実行し、アプリのインストール、デバイス シェルへのアクセス、その他の管理機能を有効にするコマンド ライン ツールです。  

### <a name="file-system-encryption"></a>ファイル システムの暗号化

Teams Android デバイスは Android ベースの暗号化をサポートする必要があり、Microsoft エンドポイント マネージャー コンプライアンス ポリシーを使用して適用できます。 エンドポイント マネージャーコンプライアンス ポリシーの詳細については、[エンドポイント マネージャー コンプライアンス ポリシーを使用して、Intuneで管理するデバイスのルールを設定](/mem/intune/protect/device-compliance-get-started)します。

### <a name="android-os-version"></a>Android OS バージョン

Teams Android デバイスでは、サポートされているバージョンの Android が実行されます。 Android オペレーティング システムは OEM パートナーによって管理され、Teams 認定ファームウェアにマージされ、Teams 管理センターからデバイスにプッシュされます。 Teams Android デバイスで実行されている Android バージョンの詳細については、 [Microsoft Teams 認定 Android デバイス](/microsoftteams/devices/teams-ip-phones)に関するページを参照してください。

### <a name="android-security-updates"></a>Android セキュリティ更新プログラム

OEM ベンダーは、ファームウェア更新プロセスの一環として、適切な Android セキュリティ更新プログラムベースラインを組み込み、基本オペレーティング システムのセキュリティを確保するのに役立ちます。 デバイスを定期的に更新しておくことは、デバイスで適切な Android セキュリティ更新プログラムが実行されていることを確認するために重要です。 詳細については、デバイスの製造元を参照してください。

### <a name="account-security"></a>アカウントのセキュリティ

Teams Android デバイスは、デバイスの正常な機能を可能にする 2 種類のアカウントを中心に構築されています。

- ローカル デバイス管理者アカウント

- ユーザーまたはリソース アカウント  

Teams Android デバイスは、一部の条件付きアクセス ポリシーとも互換性があります。これは、デバイス サインインのセキュリティの追加レイヤーとして使用できます。 ベスト プラクティスとサポートされている条件付きアクセス ポリシーについては、「 [サポートされている条件付きアクセス コンプライアンス ポリシー](/microsoftteams/rooms/supported-ca-and-compliance-policies)」を参照してください。

### <a name="local-device-administrator-account"></a>ローカル デバイス管理者アカウント

Teams Android デバイスには、デバイス設定にアクセスするための管理アカウント、インストールされている場合はローカル Web サーバー、OEM 固有の設定が含まれます。

このアカウントの既定のユーザー名やパスワードなどの初期デバイスのセットアップと構成項目は、デバイスの製造元から取得できます。

> [!CAUTION]
> できるだけ早くローカル デバイス管理者のパスワードを変更してください。  

> [!TIP]
> Teams 管理センターを使用すると、構成プロファイルを適用して、サインインしている Teams Android デバイスのローカル デバイス管理者パスワードを変更できます。 Android デバイスの管理者特権の機能を保護するには、最初のデバイス サインイン後にこの方法をお勧めします。 管理者特権の機能には、デバイス設定と Web 管理ポータルがサポートされている場合に含めることができます。

### <a name="user-or-resource-account"></a>ユーザーまたはリソース アカウント

Teams Android デバイスでは、Microsoft 365 にサインインするために、ユーザーまたは専用リソース アカウントを使用する必要があります。 個人用デバイスの通常のユーザー アカウントか、共有デバイスのリソース アカウントであるかに応じて、これらのアカウントを特定の方法でセキュリティで保護しようとします。 詳細については、「 [会議室と共有デバイスのリソース アカウントを作成して構成する](/microsoftteams/rooms/with-office-365)」を参照してください。

### <a name="device-updates"></a>デバイスの更新

Teams Android デバイスは、Microsoft 認定の更新プログラムを Teams 管理センターからダウンロードするように構成されています。 これらは、管理者が自動的にプッシュするか、手動で呼び出すことができます。 必要に応じて、OEM パートナーのサード パーティ製ツールを使用して、この機能を実行することもできます。 Teams Android デバイスは、ユーザーへの影響を回避するために、数時間後に更新プログラムをインストールできます。 時間外スケジュールは、Teams 管理センターで構成することも、OEM パートナーのサードパーティツールを使用して構成することもできます。

> [!IMPORTANT]
> Microsoft では、Teams 管理センターを使用して、すべての Teams Android デバイスのファームウェアを管理することをお勧めします。

## <a name="network-security"></a>ネットワーク セキュリティ

Teams Android デバイスには、ファイアウォールやその他のセキュリティ デバイス経由のアクセスなど、Microsoft Teams クライアントと同じネットワーク要件があります。 具体的には、Teams に **必要な** カテゴリをファイアウォールで開き、次に示すその他のサポート サービスを開く必要があります。 Teams Android デバイスに必要な IP と URL の完全な一覧については、次を参照してください。

- Microsoft Teams、Exchange Online、SharePoint Online、Microsoft 365 Common、Office Online [Office 365 URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune[のネットワーク エンドポイントをMicrosoft Intune](/mem/intune/fundamentals/intune-endpoints)する

Teams Android デバイスは、ほとんどの 802.1X およびその他のネットワーク ベースのセキュリティ プロトコルで動作します。 ただし、すべてのネットワーク セキュリティ構成に対して Teams Android デバイスをテストすることはできません。 そのため、ネットワーク パフォーマンスの問題にトレースできるパフォーマンスの問題が発生した場合は、組織で構成されている場合は、これらのプロトコルを無効にするか、OEM パートナーに問い合わせてサポートを受ける必要があります。

リアルタイム メディアの最適なパフォーマンスを得るには、プロキシ サーバーやその他のネットワーク セキュリティ デバイスをバイパスするように Teams メディア トラフィックを構成することを強くお勧めします。 リアルタイム メディアは、プロキシ サーバーやその他のネットワーク セキュリティ デバイスによって発生する可能性があるネットワーク待機時間に影響を受けます。 ネットワーク待機時間により、ユーザーのビデオとオーディオの品質が大幅に低下する可能性があります。 詳細については、「 [ネットワークアップ (クラウドへのネットワーク) -](/microsoft-365/solutions/networking-design-principles) Microsoft Teams でメディアのパフォーマンスを向上させるためのネットワークの推奨事項について説明する 1 人のアーキテクトの視点」を参照してください。

Teams Android デバイスでは、インターネット上で暗号化された通信とエンドポイント認証が使用されます。 Teams Android デバイスでは TLS 1.2 以降が使用されます。  

> [!IMPORTANT]
> Teams Android デバイスでは、認証されたプロキシ サーバーやテナントの制限はサポートされていません。 プロキシ サポート情報については、OEM パートナーにお問い合わせください。

Teams Android デバイスは、内部 LAN に接続する必要はありません。 直接インターネット にアクセスできるセキュリティで保護されたネットワーク セグメントに Teams Android デバイスを配置することを検討してください。 たとえば、Teams Phone は音声 VLAN に展開できます。 内部 LAN が侵害された場合、このネットワーク分離を実装することで、Teams Android デバイスに対する攻撃ベクトルの機会が減少します。

Teams Android デバイスを有線ネットワークに接続することを強くお勧めします。 ワイヤレス ネットワークを使用するには、最適なエクスペリエンスを得るための慎重な計画と評価が必要です。

Teams パネルの近接結合、Better Together、Teams キャスト、ペアリングは Bluetooth に依存します。 Android デバイスのTeams Roomsでの Bluetooth テクノロジの使用は、現在、ビーコンの広告に限定され、近位接続が求められます。 ビーコンのアドバタイズでは、`ADV_NONCONN_INT` プロトコル データ ユニット (PDU) 型が使用されます。 この PDU 型は、リッスンしているデバイスに情報をアドバタイズする非接続デバイス用です。 これらの機能の一部として、Bluetooth デバイスのペアリングはありません。 Bluetooth プロトコルの詳細については、Bluetooth SIG Web サイトを参照してください。

Teams Phones and Displays には、Bluetooth Hands-Free プロファイルを使用してヘッドセットとペアリングする Bluetooth ペアリング機能が用意されています。

Microsoft Teams のセキュリティの詳細については、「 [セキュリティと Microsoft Teams](/microsoftteams/teams-security-guide)」を参照してください。  
