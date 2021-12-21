---
title: 電話デバイスとディスプレイTeams展開を計画する
ms.author: czawideh
author: cazawideh
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
description: この記事では、組織の電話やディスプレイにTeamsタスクと手順について説明します。
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577797"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>電話デバイスとディスプレイTeams展開を計画する

電話デバイスとディスプレイのTeams展開が成功Teamsは、計画から始まります。 この記事では、組織にこれらのデバイスをデプロイするためのタスクと手順について説明します。 また、デバイスの使用状況、ライセンス、環境、タッチポイント、管理との統合に関するガイダンスも提供します。

> [!TIP]
> [導入Microsoft 365ハブは](https://adoption.microsoft.com/)、導入プロセスを開始する際に最適なMicrosoft Teams。

## <a name="task-1-what-are-your-deployment-objectives"></a>タスク 1: デプロイの目的は何ですか。

組織の電話とディスプレイTeams展開の計画は、展開の目標から始まります。 Teamsデバイスは、会議室、オフィス、その他の機能スペースでのハイブリッド作業をサポートします。 これらのデバイスが使用される場所と使用者を決定する必要があります。

### <a name="objective-identify-your-device-personas"></a>目的: デバイスのペルサを識別する

Teamsとディスプレイは、次の 2 つのペルサのいずれかを使用できます。 

- 個人用デバイス
- 共有スペース デバイス

個人用デバイスと共有デバイスの役割と使用方法は異なります。 

**個人用デバイス:** 

- 通常、1 人のユーザーに割り当て、そのユーザーのアカウントでサインインし、サービスにアクセスする Teams機能ライセンスを有効にします。
- 個人用デバイスは、1 対 1 の関係を持ち、1 人のユーザーにつき 1 つのデバイスと考えます。
- デスクトップ クライアントとペアTeams、Better Together のような機能を使用できます。
- ヘッドセット、有線、またはワイヤレスに接続できる
- 個人用デバイスのその他の機能には、ホットデスクやホーム画面が含まれます。 

**共有スペース デバイス:**

- 共通のエリア電話や会議室デバイスなど、特定の機能を実行し、サービスにアクセスするには専用のアカウントと機能ライセンスが必要です。
- 共有デバイスは、一対多リレーションシップを持つデバイスと考えます。1 つのデバイスは多くのユーザーによって共有されます。
- 会議室、受付エリア、製造フロアなどの共有スペースに展開されます。 
- ユーザー インターフェイス (UI) は、共通領域 電話 UI などの機能に固有のインターフェイスです。また、会議室の UI は、共有デバイスの機能と配置に依存します。
- 設定が変更されないか、アカウントのサインアウトを防ぐために、構成とオプションのセキュリティ強化が必要です。 
- 共有空間デバイスのその他の機能には、共通領域の電話での検索やアイドル タイムアウトを使用したホットデスク機能が含まれます。

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目的: 必要な個人用および共有空間デバイスの数。

デバイスのペルサを特定したので、使用する認定デバイスと必要なデバイスの数を決定する必要があります。 この決定を支援するために、次の質問を検討してください。 

- 必要な個人用デバイスの数と、必要なデバイスを持つユーザー
- 共有デバイスが必要な会議室またはスペースの数 すべての領域に同じ種類のデバイスがありますか? 
- デバイスは特定の要件を満たす必要がありますか?
    - たとえば、画面サイズ、フォーム ファクター、製造元またはモデルなどです。 認定された電話とディスプレイの一覧については、「認定デバイスのMicrosoft Teams[を参照してください](teams-ip-phones.md)。
-  携帯電話やディスプレイTeams必要Teamsですか? Teams スマートフォンでサポートされる機能の一覧については、「Microsoft Teams の[](phones-for-teams.md#features-supported-by-teams-phones)電話」を参照し、Teams ディスプレイでサポートされる機能の一覧については、「Microsoft Teams ディスプレイ」[を参照してください](teams-displays.md#features-supported-by-teams-displays)。
- 新しいユーザー用のデバイスが十分にあるか、新しい注文と配送のプロセスがありますか。
- メンテナンスまたはハードウェアの問題が発生した場合に、予備のデバイスを使用できますか。 デバイスを交換できると、ユーザー エクスペリエンスの中断がすぐに回避されます。

## <a name="task-2-what-are-your-licensing-requirements"></a>タスク 2: ライセンス要件は何ですか? 

必要なデバイスの数がわかったので、次の手順では、必要なライセンスの数を決定します。 Teamsとディスプレイにアクセスするには、電話とディスプレイにライセンスMicrosoft Teams必要Microsoft 365。

共有デバイスと個人用デバイスには、異なるライセンスが必要です。 個人用デバイスの場合、ユーザー アカウントに割り当てられたライセンスを使用できます。 共有デバイスには、その機能に固有のライセンスが必要です。 電話とディスプレイの場合、該当するライセンスは、電話 の共通領域ライセンスMicrosoft Teams、Microsoft Teams [Rooms Standard](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)ライセンスです。 [](../set-up-common-area-phones.md#step-1---buy-the-licenses)

ライセンス オプションの詳細と比較については、「ライセンス プランのMicrosoft 365[参照してください](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 

## <a name="task-3-what-are-your-dependencies"></a>タスク 3: 依存関係は何ですか? 

### <a name="objective-plan-your-device-identities"></a>目的: デバイス ID を計画する

ID を使用すると、デバイスは Microsoft 365 サービスにアクセスできます。また、デバイスを組織内で検出、管理、および接続しやすくする必要があります。 これを実現するには、デバイス ID を計画するときに次の点を考慮してください。

- ユーザー プリンシパル名とその形式とドメイン
- 表示名
- アドレス帳の検出可能性
- 個人用デバイスと共有スペース デバイスの種類
- グループ割り当てライセンスとユーザー割り当てライセンス

### <a name="objective-review-conditional-access-policies"></a>目的: 条件付きアクセス ポリシーを確認する

Azure Active Directory条件付きアクセス ポリシーは、デバイスをサインインする前に満たす必要がある追加の要件です。

デプロイを計画する場合

- 携帯電話やディスプレイに影響を与える可能性がある既存Teamsポリシーを確認します。 これは、What If ツールとサインイン Azure AD使用して[](/azure/active-directory/conditional-access/what-if-tool)、管理センターで[実行できます。](/azure/active-directory/reports-monitoring/concept-sign-ins)

- 必要に応じて新しいルールを計画する

- デバイス フィルターのような条件付きアクセス機能を使用して、携帯電話やディスプレイTeamsルールを適用します。

>[!NOTE]
>Android デバイスがサポートしない条件付きアクセス ポリシーがあります。 ガイダンスとベスト プラクティスについては、Android デバイスに関するページを参照[Teams](authentication-best-practices-for-android-devices.md)してください。

## <a name="task-4-prepare-your-environment"></a>タスク 4: 環境を準備する

### <a name="objective-plan-network-basics"></a>目的: ネットワークの基本を計画する

Teams 電話デバイスとディスプレイでは、インターネットにアクセスして、意図したTeamsに接続し、機能する必要があります。 ネットワークをデプロイする準備をするには、次の点を考慮してください。

- ネットワーク インフラストラクチャに十分な容量がありますか。 スイッチ ポート、ワイヤレス アクセス ポイント、その他のカバレッジを検討してください。
- VLAN と DHCP を使用する場合、スコープのサイズは変更されますか。
- デバイスをデプロイするネットワーク パスを評価し、テストMicrosoft 365。 
- ガイダンスに従って、要求に必要なファイアウォール Microsoft 365 URL を開きます。
- 場所の精度とコンプライアンスについて、E911 の要件と構成を確認し、テストします。 
- プロキシ サーバーを使用しないようにし、信頼性と品質のためにメディア パスを最適化します。

### <a name="objective-physical-considerations"></a>目的: 物理的な考慮事項

携帯電話やディスプレイで使用Teamsスペースを検討してください。

主な側面は次のとおりです。

- **電源:** 十分な電気コンセントはありますか? デバイスに外部電源が必要な場合は、どのくらい近くにコンセントに配置できますか?
- **デバイスの配置:** デバイスの物理的な場所 デスク スタンド、壁掛け、および OEM (元の機器メーカー) のその他のアクセサリを確認します。
- **セキュリティ:** デバイスを特定のスペースでロックする必要がありますか?
- **アクセシビリティ:** デバイスはプライマリ ユーザーのアクセシビリティ要件を満たしていますか? 配置場所、ワイヤの長さ、ハンドセットまたはヘッドセットの使いやすさを検討します。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>タスク 5: デプロイされたデバイスを管理する方法

Teamsとディスプレイは、2 ~ 3 つのポータルとそれぞれの PowerShell モジュールMicrosoft 365から管理されます。 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory管理センター

管理センター Azure AD使用して管理する

- 携帯電話とディスプレイの ID 関連Teamsタスク
- 条件付きアクセス ポリシー 
- パスワードのリセット

#### <a name="teams-admin-center"></a>Teams管理センター

管理センター Teams使用して管理する

- [デバイスの設定Teams](../business-voice/manage-devices.md)
- [構成プロファイル](device-management.md#use-configuration-profiles-in-teams)
- [デバイスのタグ付け](manage-device-tags.md)
- [リモート サインインとサインアウト](remote-sign-in-and-sign-out.md)
- 通話分析  
- ファームウェア
- ログのトラブルシューティングとダウンロード

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>エンドポイント マネージャー 管理センター (デバイス管理に Intune を使用する場合)

管理センターエンドポイント マネージャー使用して、次の情報を管理します。 

- デバイス コンプライアンス ポリシー
- 登録の制限
- 会社のデバイス識別子
- デバイス フィルター
