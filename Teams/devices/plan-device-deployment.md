---
title: Teams電話デバイスとディスプレイの展開を計画する
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
description: この記事では、組織内の電話とディスプレイTeams展開するタスクと手順について説明し、概要を説明します。
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577797"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Teams電話デバイスとディスプレイの展開を計画する

Teams電話デバイスとTeamsディスプレイの正常な展開は、計画から始まります。 この記事では、これらのデバイスを組織内に展開するためのタスクと手順について説明します。 また、デバイスの使用状況、ライセンス、環境との統合、タッチポイント、および管理に関するガイダンスも提供されます。

> [!TIP]
> [Microsoft 365導入ハブ](https://adoption.microsoft.com/)は、Microsoft Teamsを使用して導入を開始するのに最適な場所です。

## <a name="task-1-what-are-your-deployment-objectives"></a>タスク 1: デプロイの目標は何ですか?

組織内のTeams電話とディスプレイのロールアウトの計画は、展開の目標から始まります。 Teams デバイスは、会議室、オフィス、その他の機能空間でのハイブリッド作業をサポートします。 これらのデバイスを使用する場所と使用者を特定する必要があります。

### <a name="objective-identify-your-device-personas"></a>目標: デバイスペルソナを特定する

Teams電話とディスプレイは、次の 2 つのペルソナのいずれかに適合します。 

- 個人用デバイス
- 共有スペース デバイス

個人用デバイスと共有デバイスの役割と使用方法は異なります。 

**個人用デバイス:** 

- 通常、1 人のユーザーに割り当てられ、そのユーザーのアカウントでサインインし、サービスにアクセスするためのTeams機能ライセンスで有効になります。
- 個人用デバイスは、1 人のユーザーにつき 1 台のデバイスで、1 対 1 のリレーションシップを持つと考えてください。
- Teams デスクトップ クライアントとペアリングでき、Better Together などの機能を使用できます
- ヘッドセット、ワイヤード(有線)、またはワイヤレスに接続できます
- 個人用デバイスのその他の機能には、ホットデスクとホーム画面が含まれます。 

**共有スペース デバイス:**

- 共通エリアの電話や会議室デバイスなどの特定の機能を実行し、サービスにアクセスするには専用のアカウントと機能ライセンスが必要です。
- 共有デバイスは、多くのユーザーが共有する 1 つのデバイスという 1 対多のリレーションシップを持つと考えてください。
- 会議室、受付エリア、製造フロアなどの共有スペースに展開されます。 
- ユーザー インターフェイス (UI) は、Common Area 電話 UI や会議室 UI など、その機能に固有です。共有デバイスの機能と配置によって異なります。
- 設定が変更されないようにしたり、アカウントがサインアウトできないようにしたりするには、構成とセキュリティ強化を必要とします。 
- 共有スペース デバイスのその他の機能には、共通領域の電話での検索や、アイドル タイムアウトを伴うホット デスク処理などがあります。

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目標: 必要な個人用と共有スペースのデバイスの数はどれくらいですか?

デバイスペルソナを特定したので、使用する認定デバイスと必要なデバイスの数を決定する必要があります。 この決定に役立つには、次の質問を検討してください。 

- 必要な個人用デバイスの数と、必要な個人デバイスの数はどれですか?
- 共有デバイスを必要とする会議室またはスペースの数はどれくらいですか? すべての領域に同じ種類のデバイスがありますか? 
- デバイスは特定の要件を満たす必要がありますか?
    - たとえば、画面サイズ、フォーム ファクター、製造元またはモデルなどです。 認定された電話とディスプレイの一覧については、[認定されたデバイスMicrosoft Teams](teams-ip-phones.md)参照してください。
-  電話またはTeamsディスプレイTeams必要がありますか? Teamsスマートフォンでサポートされている機能の一覧については、「[Microsoft Teams用の電話](phones-for-teams.md#features-supported-by-teams-phones)」と、Teamsディスプレイでサポートされている機能の一覧については、「[Microsoft Teamsディスプレイ」を](teams-displays.md#features-supported-by-teams-displays)参照してください。
- 新しいユーザーに十分なデバイスがあるか、新しい注文と配送のためのプロセスがありますか?
- メンテナンスやハードウェアの問題が発生した場合に、予備のデバイスを使用できますか? デバイスを交換できることで、ユーザー エクスペリエンスの中断を迅速に防ぎます。

## <a name="task-2-what-are-your-licensing-requirements"></a>タスク 2: ライセンス要件は何ですか? 

必要なデバイスの数がわかったら、次の手順では、必要なライセンスの数を決定します。 Teams電話とディスプレイでは、Microsoft TeamsとMicrosoft 365にアクセスするためのライセンスが必要です。

共有デバイスと個人用デバイスには、異なるライセンスが必要です。 個人用デバイスの場合は、ユーザー アカウントに割り当てられたライセンスを使用できます。 共有デバイスには、その機能に固有のライセンスが必要です。 電話とディスプレイの場合、該当するライセンスは、[Microsoft TeamsおよびMicrosoft Teams Rooms Standard ライセンスの共通領域](../set-up-common-area-phones.md#step-1---buy-the-licenses)[電話 ライセンス](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)です。

ライセンス オプションの詳細と比較については、「[Microsoft 365 ライセンス プラン](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)」を参照してください。 

## <a name="task-3-what-are-your-dependencies"></a>タスク 3: 依存関係は何ですか? 

### <a name="objective-plan-your-device-identities"></a>目標: デバイス ID を計画する

ID を使用すると、デバイスはMicrosoft 365サービスにアクセスでき、デバイスは組織内で簡単に検出、管理、接続できるようになります。 これを実現するには、デバイス ID を計画する際に、次の点を考慮してください。

- ユーザー プリンシパル名とその形式とドメイン
- 表示名
- アドレス帳の検出可能性
- 個人用デバイスと共有空間のデバイスの種類
- グループとユーザー割り当てライセンス

### <a name="objective-review-conditional-access-policies"></a>目標: 条件付きアクセス ポリシーを確認する

Azure Active Directory条件付きアクセス ポリシーは、デバイスをサインインする前に満たす必要がある追加の要件です。

デプロイを計画する際

- Teamsの電話やディスプレイに影響を与える可能性がある既存の条件付きアクセス ポリシーを確認します。 What [If ツール](/azure/active-directory/conditional-access/what-if-tool)と[サインイン ログ](/azure/active-directory/reports-monitoring/concept-sign-ins)を使用して、Azure AD管理センターでこれを行うことができます

- 必要に応じて新しいルールを計画する

- デバイス フィルターなどの条件付きアクセス機能を使用して、Teams電話やディスプレイにルールを適用します。

>[!NOTE]
>Android デバイスではサポートされていない条件付きアクセス ポリシーがいくつかあります。 ガイダンスとベスト プラクティスについては、Android デバイスに関するページTeams [Android デバイスの認証のベスト プラクティス](authentication-best-practices-for-android-devices.md)に関するページを参照してください。

## <a name="task-4-prepare-your-environment"></a>タスク 4: 環境を準備する

### <a name="objective-plan-network-basics"></a>目標: ネットワークの基本を計画する

Teams 電話デバイスとディスプレイでは、インターネットにアクセスしてTeamsに接続し、意図したとおりに機能する必要があります。 ネットワークをデプロイする準備を整えるには、次の点を考慮してください。

- ネットワーク インフラストラクチャに十分な容量がありますか? スイッチ ポート、ワイヤレス アクセス ポイント、およびその他のカバレッジについて検討します。
- VLAN と DHCP を使用する場合、スコープはそれに応じてサイズ設定されますか?
- デバイスがMicrosoft 365に展開される場所からネットワーク パスを評価し、テストします。 
- ガイダンスに従って、Microsoft 365に必要なファイアウォール ポートと URL を開きます。
- E911 の要件と構成を確認してテストし、場所の正確性とコンプライアンスを確認します。 
- プロキシ サーバーの使用を避け、信頼性と品質のためにメディア パスを最適化します。

### <a name="objective-physical-considerations"></a>目標: 物理的な考慮事項

Teams電話とディスプレイが使用される物理空間について考えてみましょう。

主な側面は次のとおりです。

- **電源：** コンセントは十分ですか? デバイスに外部電源が必要な場合は、コンセントにどの程度近く配置できますか?
- **デバイスの配置:** デバイスは物理的にどこにありますか? 元の機器メーカー (OEM) のデスク スタンド、壁取り付け、その他のアクセサリを確認します。
- **セキュリティ：** デバイスを特定のスペースにロックする必要がありますか?
- **アクセシビリティ：** デバイスはプライマリ ユーザーのアクセシビリティ要件を満たしていますか? 配置場所、ワイヤの長さ、受話器またはヘッドセットの使いやすさを検討してください。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>タスク 5: 展開されたデバイスを管理する方法

Teams電話とディスプレイは、2 つから 3 つのMicrosoft 365 ポータルとそれぞれの PowerShell モジュールから管理されます。 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory管理センター

Azure AD管理センターを使用して管理する

- Teams電話とディスプレイのすべての ID 関連タスク
- 条件付きアクセス ポリシー 
- パスワードのリセット

#### <a name="teams-admin-center"></a>Teams管理センター

Teams管理センターを使用して管理する

- [Teamsのデバイス設定](../business-voice/manage-devices.md)
- [構成プロファイル](device-management.md#use-configuration-profiles-in-teams)
- [デバイスのタグ付け](manage-device-tags.md)
- [リモート サインインとサインアウト](remote-sign-in-and-sign-out.md)
- 通話分析  
- ファームウェア
- ログのトラブルシューティングとダウンロード

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>エンドポイント マネージャー管理センター (デバイス管理にIntuneを使用する場合)

エンドポイント マネージャー管理センターを使用して管理します。 

- デバイス コンプライアンス ポリシー
- 登録の制限
- 会社のデバイス識別子
- デバイス フィルター
