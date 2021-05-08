---
title: Microsoft Teams パネル
ms.author: v-mdhiman
author: ManikaDhiman
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: この記事では、各パネルでサポートされる機能と機能の概要Microsoft Teamsします。
ms.openlocfilehash: 5588448bfbde95747c7f02f150deae24de51f55a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102143"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams パネル

Microsoft Teamsパネルは、会議スペースの外 (通常は入口の横) の外に取り付けられているコンパクトなタッチスクリーン デバイスです。 Teamsパネルを使用すると、場所と会議の詳細を一目で確認し、その場で利用可能な会議スペースを予約できます。 豊富な大きなテキストと色分けされたインジケーターを使用すると、離れた場所から会議スペースの空き時間情報を確認できます。

Teamsパネルは、Microsoft Teams 365 カレンダー アプリケーションを介してスケジュールされた会議の詳細Teams表示Outlook専用のデバイスです。 会議の詳細が目立つように表示された場合、出席者は、適切な会議スペース、適切な時刻、および適切な会議に参加しているユーザーを確認できます。

この記事では、Teamsパネルの概要を説明し、組織内の Teams パネル デバイスの計画、配信、管理に役立ちます。

## <a name="features-supported-by-teams-panels"></a>一部のパネルでTeams機能

Teamsは、次の機能をサポートします。

- **会議スペースと会議の詳細の専用表示。** 場所や空き時間情報など、会議スペースに関する詳細が一目でわかります。 予約された会議スペースでは、会議のタイトル、会議のスケジュール、会議の開催者などの主要な会議の詳細を確認できます。
- **臨時の会議に使用できる会議スペースを予約します。** タッチスクリーン パネルを使用すると、その場で臨時会議用に利用可能な会議スペースを予約し、その Teams 会議に、会議室の Microsoft Teams ミーティング デバイスまたは Surface Hub デバイスから参加できます。
- **空き領域の状態を示す色分けされたインジケーター。** 鮮やかな LED とホーム画面インジケーターを使用して、会議スペースの空き時間情報を確認できます。 [緑] は会議スペースが利用可能な状態を示し、必要に応じてパネル自体から予約できます。 赤または紫は、会議スペースが予約済みかどうかを示します。
- **壁紙と予約状態インジケーターをカスタマイズします。** 管理者は、設定を使用してパネルの既定の外観を変更できます。 たとえば、管理者は背景の壁紙を変更したり、ビジー状態インジケーターの色を変更したりすることができます。
- **アクセシビリティ。** Teamsパネルには、ハイ コントラスト テキストなど、ユーザーが簡単に使用できるアクセシビリティ機能があります。

これらの機能の詳細と、その使い方については、「Use Microsoft Teams panels 」[を参照してください](use-teams-panels.md)。

## <a name="partners-certified-for-teams-panels"></a>パネルの認定Teamsパートナー

次のいずれかのパートナー Teamsパネル デバイスを取得できます。

- クレスロン
- (近日公開予定)Yealink

## <a name="teams-panels-requirements"></a>Teamsパネルの要件

パネル デバイスを展開するハードウェア、ソフトウェア、ネットワークの要件は、展開するパネル デバイスの種類によって異なる場合があります。 一連のデバイスに必要な情報については、OEM (Original Equipment Manufacturer) のドキュメントを参照してください。

## <a name="license-requirement"></a>ライセンス要件

このパネルTeamsするには、Standard License [Microsoft Teams ミーティング必要があります](../rooms/rooms-licensing.md)。

> [!Note]
> Teams パネルをインストールする会議スペースに Microsoft Teams ミーティング を既に展開している場合は、Teams パネルを使用するために追加のライセンスは必要ない。

## <a name="deploy-teams-panels-devices"></a>パネル Teamsをデプロイする

パネル デバイスの計画、デプロイ、管理にTeams場合は、このセクションを参照してください。 このセクションは、パネルのエンド ユーザーを対象Teamsです。

パネル デバイスTeamsのデプロイは、次のタスクに分けられます。

- [会議スペースのインベントリと機能計画](#inventory-sites-and-meeting-spaces): 複数のパネル デバイスをデプロイするために、組織のサイトと会議スペースTeams作成します。
- [調達](#procurement): 選択したデバイス パートナーからデバイスを調達します。  
- [サイトの準備](#site-readiness): 展開場所 (会議スペース) が展開要件を満たしていることを確認します。
- [構成とデプロイ](#configuration-and-deployment): リソース アカウントを作成し、デバイスに割り当てる。

## <a name="inventory-sites-and-meeting-spaces"></a>サイトと会議スペースのインベントリ

組織内の既存の予約可能な会議スペースのインベントリを作成します。 複数のパネルを展開する対象のサイトと会議スペースTeamsします。 施設やオーディオ ビジュアル チームと一緒に作業し、Teams パネル デバイスをインストールする場所と方法、およびパネルを取り付ける追加のハードウェアが必要かどうかを判断します。

## <a name="procurement"></a>調達

Teams パネルを展開する対象の会議スペースの数に基づいて、Teams パネルの認定を受けたパートナーの 1 つから[デバイスを調達します](#partners-certified-for-teams-panels)。 デバイスと調達オプションの詳細については、パートナーの Web サイトを参照してください。

組織内の会議スペースには、デバイスのインストールまたはマウントに関するハードウェア要件が異なる場合があります。 たとえば、デバイスをガラス、ガラス、ドライウォール、または木のパネルに取り付けるのに必要なハードウェアは、同じではない可能性があります。 使用可能なマウント オプションについては、デバイス パートナーのドキュメントを参照してください。

## <a name="site-readiness"></a>サイトの準備

注文されたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと共同で、展開要件が満たされ、各サイトと会議スペースが電源とネットワークの面で準備ができていることを確認します。

パネル サイトに関Teams推奨事項は次のとおりです。

- 専用リソース アカウント
- 電源 (パネルは一般に、電源に対して Power over Ethernet + (PoE+) をサポートします。 デバイス固有の電源要件については、OEM のドキュメントを参照してください)。


物理的なインストールに関する考慮事項については、OEM のドキュメントを参照し、ある場合は、デバイスをインストールしてマウントし、ケーブル接続を実行する前に、オーディオ ビジュアル チームのエクスペリエンスを使用してください。

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- テスト

### <a name="resource-account-provisioning"></a>リソース アカウントのプロビジョニング

すべてのTeams パネル デバイスには、Microsoft 365 のリソース アカウントが必要です。 リソース アカウントの資格情報を使用して、パネル デバイスMicrosoft Teamsアプリにサインインします。

各パネルにMicrosoft 365リソース アカウントをTeamsするには、Standard ライセンス を購入Microsoft Teams ミーティング[勧めします](#license-requirement)。 リソース アカウントを作成し、そのアカウントにライセンスを割り当てる方法については、「管理センターを使用してリソース アカウントを作成する[Microsoft 365参照してください](resource-account-ui.md)。

> [!NOTE]
>
>- パネルをインストールする会議スペース用に会議室リソース アカウントが既に設定されている場合は、同じ会議室リソース アカウントを使用してパネル デバイスにサインインします。 ただし、パネル リソース アカウントとして使用するには、Microsoft Teams ミーティング Standard ライセンスがルーム リソース アカウントに割り当てられている必要があります。
>
>- Teams パネルをインストールする会議スペースに Microsoft Teams ミーティング が既に展開されている場合は、パネルを展開するために別のライセンスを購入する必要があります。 管理者は、同じ領域に対して同じ資格情報を使用してMicrosoft Teams ミーティングデバイスにサインインします。
>
>- ボード ルームや会議室などの大規模な会議スペースに複数の入口がある場合は、各入口に 1 つのパネル デバイスをマウントできます。 1 つの会議スペースに属する複数のパネルが同じリソース アカウントを共有し、同じ資格情報でサインインします。 同じ領域のパネルごとに個別のリソース アカウントを作成する必要はありません。

> [!TIP]
> 実際のリソース パネルのインストールの前に、リソース アカウントTeamsお勧めします。
> パネルリソース アカウントの名前付け規則Teams使用を検討してください。 リソース アカウントの表示名をわかりやすいMicrosoft 365わかりやすい名前にします。 これらの名前は、ユーザーが会議スペースを検索するときに表示される名前で、OutlookまたはTeamsします。

### <a name="testing"></a>テスト

パネルをデプロイした後、それらをテストする必要があります。 デプロイされた[デバイスで、パネルでTeams機能](#features-supported-by-teams-panels)が動作している必要があります。 コンピューター上の 365 を使用して、Teamsまたは Outlookに対して複数の会議を作成してみてください。 パネルに、スケジュールされた会議の会議の詳細と空き時間情報が正しく表示されていることを確認します。 [予約] **ボタンを** 使用して、利用可能な会議スペースをデバイスから直接予約できるのか確認してみてください。

## <a name="manage-teams-panels-in-your-organization"></a>組織内Teamsパネルを管理する

Teams パネル デバイスを管理するには、Microsoft Teams 管理センターの左側のナビゲーションで、[デバイス] パネルにTeams  >  **します**。 ここから、デバイス構成プロファイルの変更、更新の管理、デバイスの再起動、デバイス タグの追加と削除を行えます。 詳細については、「デバイスを管理[する」を参照Teams。](device-management.md)

## <a name="next-steps"></a>次の手順

[パネル デバイスをMicrosoft Teamsする方法](use-teams-panels.md)

## <a name="see-also"></a>関連項目

[Microsoft Teamsパネルに関するTeamsブログ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[パネルの使用Teamsする](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Teamsパネル マーケットプレース](https://www.microsoft.com/microsoft-teams/across-devices/devices/product?deviceid=815)

[デバイス パネル認定プログラムMicrosoft Teams認定デバイス](teams-ip-phones.md#currently-certified-teams-panels)