---
title: Teams の電話デバイスとディスプレイの展開を計画する
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: この記事では、Teams 電話とディスプレイを組織に展開するためのタスクと手順の概要について説明します。
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 4ba5c1a9ab59765a5a0af2ac145baf69fc4a8a9a
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392517"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Teams の電話デバイスとディスプレイの展開を計画する

Teams 電話デバイスと Teams ディスプレイの正常な展開は、計画から始まります。 この記事では、これらのデバイスを組織内に展開するためのタスクと手順について説明します。 また、デバイスの使用状況、ライセンス、環境、タッチポイント、管理との統合に関するガイダンスも提供します。

> [!TIP]
> [Microsoft 365 導入ハブ](https://adoption.microsoft.com/)は、Microsoft Teams での導入体験を開始するのに最適な場所です。

## <a name="task-1-what-are-your-deployment-objectives"></a>タスク 1: デプロイの目的は何ですか?

組織内の Teams 電話とディスプレイのロールアウトの計画は、展開の目標から始まります。 Teams デバイスは、会議室、オフィス、その他の機能空間でのハイブリッド作業をサポートします。 これらのデバイスを使用する場所とユーザーを決定する必要があります。

### <a name="objective-identify-your-device-personas"></a>目的: デバイスペルソナを特定する

Teams の電話とディスプレイは、次の 2 つのペルソナのいずれかに適合します。 

- 個人用デバイス
- 共有スペース デバイス

個人用デバイスと共有デバイスの役割と使用方法は異なります。 

**個人用デバイス:** 

- 通常、1 人のユーザーに割り当てられ、そのユーザーのアカウントでサインインし、Teams 機能ライセンスを使用してサービスにアクセスできるようになりました。
- 個人のデバイスは、1 人のユーザーごとに 1 つのデバイスと 1 対 1 の関係があると考えてください。
- Teams デスクトップ クライアントとペアリングし、Better Together などの機能を使用できます
- ヘッドセット、有線、またはワイヤレスに接続できます
- 個人用デバイスのその他の機能には、ホット デスクとホーム画面があります。 

**共有スペース デバイス:**

- 共通エリア電話や会議室デバイスなどの特定の機能を実行し、サービスにアクセスするには専用のアカウントと機能ライセンスが必要です。
- 共有デバイスは、1 対多の関係を持つと考えてください。1 つのデバイスは多くのユーザーによって共有されます。
- 会議室、レセプションエリア、製造フロアなどの共有スペースに展開されます。 
- ユーザー インターフェイス (UI) は、共通領域の電話 UI や会議室 UI などの機能に固有であり、共有デバイスの機能と配置に依存します。
- 設定が変更されないように、またはアカウントがサインアウトしないように、構成とオプションのセキュリティ強化が必要です。 
- 共有スペース デバイスのその他の機能には、共通エリアの電話での検索、アイドル タイムアウトによるホット デスクなどがあります。

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目的: 必要な個人用および共有スペース デバイスの数

デバイスペルソナを特定したので、使用する認定デバイスと必要なデバイスの数を決定する必要があります。 この決定を支援するには、次の質問を検討してください。 

- 必要な個人用デバイスの数と、そのデバイスを持つユーザーはどれですか?
- 共有デバイスが必要な部屋またはスペースはいくつですか? すべての領域に同じ種類のデバイスがありますか? 
- デバイスは特定の要件を満たす必要がありますか?
    - 例としては、画面サイズ、フォーム ファクター、製造元またはモデルが含まれます。 認定された電話とディスプレイの一覧については、「[Microsoft Teams 認定デバイス](teams-ip-phones.md)」を参照してください。
-  Teams 電話または Teams ディスプレイが必要ですか? Teams 電話でサポートされる機能の一覧については、「[Microsoft Teams の電話](phones-for-teams.md#features-supported-by-teams-phones)」を参照してください。 Teams ディスプレイでサポートされている機能の一覧については、「teams ディスプレイ[Microsoft](teams-displays.md#features-supported-by-teams-displays)」を参照してください。
- 新しいユーザーに十分なデバイスがありますか、または新しい注文と配送のプロセスがありますか?
- 予備のデバイスをメンテナンスに使用できますか、またはデバイスでハードウェアの問題が発生した場合は、 デバイスを迅速にスワップできるため、ユーザー エクスペリエンスの中断を防ぐことができます。

## <a name="task-2-what-are-your-licensing-requirements"></a>タスク 2: ライセンス要件は何ですか? 

必要なデバイスの数が分かります。次の手順では、必要なライセンスの数を決定します。 Teams の電話とディスプレイには、Teams と Microsoft 365 Microsoftアクセスするためのライセンスが必要です。

共有デバイスと個人用デバイスには、異なるライセンスが必要です。 個人用デバイスの場合は、ユーザー アカウントに割り当てられたライセンスを使用できます。 共有デバイスには、その機能に固有のライセンスが必要です。 電話とディスプレイの場合、該当するライセンスは[、Microsoft Teams 共有デバイス ライセンス](/microsoftteams/teams-add-on-licensing/teams-shared-device-license)と[Microsoft Teams Rooms ライセンスです](../rooms/rooms-licensing.md)。

ライセンス オプションの詳細と比較については、「[Microsoft 365 ライセンス プラン](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」を参照してください。

## <a name="task-3-what-are-your-dependencies"></a>タスク 3: 依存関係は何ですか? 

### <a name="objective-plan-your-device-identities"></a>目的: デバイス ID を計画する

ID を使用すると、デバイスMicrosoft 365 サービスにアクセスでき、組織内でデバイスを検出、管理、接続しやすくなります。 これを実現するには、デバイス ID を計画するときに次の点を考慮してください。

- ユーザー プリンシパル名とその形式とドメイン
- 表示名
- アドレス帳の検出可能性
- 個人用デバイスと共有スペース デバイスの種類
- グループとユーザー割り当てライセンス

### <a name="objective-review-conditional-access-policies"></a>目的: 条件付きアクセス ポリシーを確認する

Azure Active Directory 条件付きアクセス ポリシーは、デバイスをサインインする前に満たす必要がある追加の要件です。

デプロイを計画する際

- Teams の電話やディスプレイに影響する可能性がある既存の条件付きアクセス ポリシーを確認します。 これは、[What If ツール](/azure/active-directory/conditional-access/what-if-tool)と[サインイン ログ](/azure/active-directory/reports-monitoring/concept-sign-ins)を使用して、Azure AD 管理 センターで行うことができます

- 必要に応じて新しいルールを計画する

- デバイス フィルターなどの条件付きアクセス機能を使用して、Teams の電話やディスプレイにルールを適用します。

>[!NOTE]
>Android デバイスでサポートされていない条件付きアクセス ポリシーがいくつかあります。 ガイダンスとベスト プラクティスについては、「Android デバイス」を参照してください。 [「Teams Android デバイスの認証のベスト プラクティス](authentication-best-practices-for-android-devices.md)」を参照してください。

## <a name="task-4-prepare-your-environment"></a>タスク 4: 環境を準備する

### <a name="objective-plan-network-basics"></a>目的: ネットワークの基本を計画する

Teams 電話のデバイスとディスプレイでは、Teams に接続し、意図したとおりに機能するためにインターネットにアクセスする必要があります。 ネットワークをデプロイする準備を整えるには、次の点を考慮してください。

- ネットワーク インフラストラクチャには十分な容量がありますか? スイッチ ポート、ワイヤレス アクセス ポイント、およびその他のカバレッジを検討してください。
- VLAN と DHCP を使用する場合、スコープのサイズは適切ですか?
- Microsoft 365 にデバイスを展開する場所からのネットワーク パスを評価してテストします。 
- ガイダンスに従って、Microsoft 365 に必要なファイアウォール ポートと URL を開きます。
- 場所の精度とコンプライアンスについて E911 の要件と構成を確認してテストします。 
- プロキシ サーバーの使用を避け、信頼性と品質のためにメディア パスを最適化します。

### <a name="objective-physical-considerations"></a>目的: 物理的な考慮事項

Teams の電話とディスプレイが使用される物理的なスペースを検討してください。

主な側面は次のとおりです。

- **電源：** コンセントは十分ですか? デバイスに外部電源が必要な場合は、コンセントにどの程度近い位置に配置できますか?
- **デバイスの配置:** デバイスは物理的にどこにありますか? オリジナル機器メーカー (OEM) のデスク スタンド、壁掛け、その他のアクセサリを確認します。
- **セキュリティ：** デバイスを特定のスペースにロックする必要がありますか?
- **アクセシビリティ：** デバイスはプライマリ ユーザーのアクセシビリティ要件を満たしていますか? 配置場所、ワイヤの長さ、ハンドセットまたはヘッドセットの使いやすさを検討してください。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>タスク 5: 展開されたデバイスを管理する方法

Teams の電話とディスプレイは、2 つから 3 つのMicrosoft 365 ポータルとそれぞれの PowerShell モジュールで管理されます。 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory 管理 センター

Azure AD 管理 センターを使用して管理する

- Teams の電話とディスプレイのすべての ID 関連タスク
- 条件付きアクセス ポリシー 
- パスワードリセット

#### <a name="teams-admin-center"></a>Teams 管理 センター

Teams 管理 センターを使用して管理する

- [Teams のデバイス設定](../business-voice/manage-devices.md)
- [構成プロファイル](device-management.md#use-configuration-profiles-in-teams)
- [デバイスのタグ付け](manage-device-tags.md)
- [リモート サインインとサインアウト](remote-sign-in-and-sign-out.md)
- 通話分析  
- ファームウェア
- ログのトラブルシューティングとダウンロード

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager 管理 Center (デバイス管理にIntuneを使用する場合)

エンドポイント マネージャー 管理 センターを使用して、次の管理を行います。 

- デバイス コンプライアンス ポリシー
- 登録の制限
- 会社のデバイス識別子
- デバイス フィルター
