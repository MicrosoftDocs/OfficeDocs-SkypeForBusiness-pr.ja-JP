---
title: Microsoft Teams のパネル
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
description: この記事では、Microsoft Teams パネルでサポートされる機能の概要と機能について説明します。
ms.openlocfilehash: 913924e62483c1a8d44bfade29e5bc700f92b646
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568923"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams のパネル

Microsoft Teams のパネルは、会議スペースの外に取り付けられているコンパクトなタッチスクリーン デバイスで、通常は入り口の横に表示されます。 Teams のパネルでは、場所と会議の詳細を一目で確認し、その場で利用可能なミーティング スペースを予約することができます。 豊富な大きなテキストと色分けされたインジケーターを使用すると、離れた場所からミーティング スペースの空き時間を確認できます。

Teams パネルは専用の Microsoft Teams デバイスで、Teams または Outlook 365 の予定表アプリケーションでスケジュールされた会議の詳細を表示します。 会議の詳細が目立つように表示された出席者は、適切なミーティング スペース、適切な時間、適切な会議に参加している確認を行います。

この記事では、Teams パネルの概要を説明し、組織内の Teams パネル デバイスの計画、配信、管理に役立ちます。

## <a name="features-supported-by-teams-panels"></a>Teams パネルでサポートされる機能

Teams のパネルは、次の機能をサポートします。

- **ミーティング スペースと会議の詳細の専用表示。** ミーティング スペースの場所や空き時間など、詳細を一目で確認できます。 予約されたミーティング スペースでは、会議のタイトル、会議のスケジュール、会議の開催者などの重要な会議の詳細を表示できます。
- **臨時の会議用に利用可能なミーティング スペースを予約します。** タッチスクリーン パネルを使用すると、臨時の会議用に、その場で利用可能なミーティング スペースを予約し、会議室の Microsoft Teams 会議室または Surface Hub デバイスから Teams 会議に参加できます。
- **空き領域の状態を示す色分けされたインジケーター。** 活気に満ちた LED とホーム画面のインジケーターを使って、離れた場所から近くでミーティング スペースの空き時間を確認できます。 緑は会議スペースが利用可能な場所を示し、必要に応じて、パネル自体から予約することができます。 赤または紫は、会議スペースが予約済みかどうかを示します。
- **壁紙と予約状態インジケーターをカスタマイズします。** 管理者は、設定を使用してパネルの既定の外観を変更できます。 たとえば、管理者は背景の壁紙を変更したり、取り込み中の状態インジケーターの色を変更できます。
- **アクセシビリティ。** Teams のパネルには、ハイ コントラスト テキストなどのアクセシビリティ機能がいくつか備え付け、誰でも簡単に使用できます。

これらの機能と使い方の詳細については [、「Microsoft Teams](use-teams-panels.md)パネルを使用する」を参照してください。

## <a name="partners-certified-for-teams-panels"></a>Teams パネルの認定パートナー

Teams パネル デバイスは、次のいずれかのパートナーから入手できます。

- クナロン
- (近日公開予定)Yealink

## <a name="teams-panels-requirements"></a>Teams パネルの要件

パネル デバイスを展開するハードウェア、ソフトウェア、ネットワーク要件は、展開するパネル デバイスの種類によって異なる場合があります。 デバイス セットに必要な情報については、元の機器製造元 (OEM) のドキュメントを参照してください。

## <a name="license-requirement"></a>ライセンス要件

Teams パネルを使用するには [、Microsoft Teams Rooms Standard License が必要です](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing)。

> [!Note]
>
> - Teams パネルをインストールするミーティング スペースに Microsoft Teams 会議室が既に展開されている場合は、Teams パネルを使用するために追加のライセンスは必要ない。
> - 近日公開される追加の高度な Teams パネル機能を使用するには、Microsoft Teams Rooms Premium のライセンスが必要です。

## <a name="deploy-teams-panels-devices"></a>Teams パネル デバイスを展開する

Teams パネル デバイスの計画、展開、管理に関わっている場合は、このセクションが最適です。 このセクションは、Teams パネルのエンド ユーザーを対象にしています。

Teams パネル デバイスの展開は、次のタスクに分けられます。

- [ミーティング スペースのインベントリと機能の計画](#inventory-sites-and-meeting-spaces): Teams パネル デバイスを展開するために、組織のサイトとミーティング スペースのインベントリを作成します。
- [調達](#procurement): 選択したデバイス パートナーからデバイスを調達します。  
- [サイトの準備](#site-readiness): 展開場所 (会議スペース) が展開要件を満たしていることを確認します。
- [構成と展開](#configuration-and-deployment): リソース アカウントを作成し、デバイスに割り当てる。

## <a name="inventory-sites-and-meeting-spaces"></a>サイトと会議スペースのインベントリ

組織内の既存の予約可能なミーティング スペースのインベントリを作成します。 Teams パネルの展開の対象であるサイトと会議スペースを特定します。 施設やオーディオ ビジュアル チームと一緒に、Teams パネル デバイスをインストールする場所と方法、およびパネルのマウントに追加のハードウェアが必要かどうかを判断します。

## <a name="procurement"></a>調達

Teams パネルの展開の範囲にある会議スペースの数に基づいて、Teams パネルの認定を受けたパートナーの 1 つからデバイス [を調達します](#partners-certified-for-teams-panels)。 デバイスと調達オプションの詳細については、パートナーの Web サイトを参照してください。

組織の会議スペースには、デバイスをインストールまたはマウントする場合、ハードウェア要件が異なる場合があります。 たとえば、デバイスをガラス、装飾、ドライ壁、または木パネルに取り付けるのに必要なハードウェアが同じではない場合があります。 使用可能なマウント オプションについては、デバイス パートナーのドキュメントを参照してください。

## <a name="site-readiness"></a>サイトの準備

注文されたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと共同で、展開要件が満たされ、各サイトとミーティング スペースが電源とネットワークの面で準備が整っていることを確認します。

Teams パネル サイトに関する推奨事項は次のとおりです。

- 専用リソース アカウント
- 電源アダプター (パネルは、通常、電源に対して Power over Ethernet Plus (PoE+) をサポートします。 デバイス固有の電源要件については、OEM ドキュメントを参照してください)。
- Microsoft Teams のネットワークで有効になっているサービスの品質 (QoS)

物理的なインストールに関する考慮事項については、OEM ドキュメントを参照し、ある場合は、デバイスをインストールしてマウントし、ケーブルを実行する前に、オーディオ ビジュアル チームのエクスペリエンスを使用してください。

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- テスト

### <a name="resource-account-provisioning"></a>リソース アカウントのプロビジョニング

すべての Teams パネル デバイスには、Microsoft 365 のルーム リソース アカウントが必要です。 リソース アカウントの資格情報を使用して、パネル デバイスで Microsoft Teams アプリにサインインします。

Teams パネルに Microsoft 365 リソース アカウントを設定するには、Microsoft Teams Rooms Standard ライセンスを [購入する必要があります](#license-requirement)。 このライセンスには、組織内のユーザーが Outlook または Teams 経由でミーティング スペースを予約できるリソース メールボックスが含まれています。

リソース アカウントを作成し、そのアカウントにライセンスを割り当てる方法については [、「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」を参照してください。

> [!NOTE]
>
>- パネルをインストールするミーティング スペース用に会議室リソース アカウントが既に設定されている場合は、同じ会議室リソース アカウントを使用してパネル デバイスにサインインします。 ただし、パネル リソース アカウントとして使用するには、会議室リソース アカウントに Microsoft Teams Rooms Standard ライセンスが割り当てられている必要があります。
>
>- Teams パネルをインストールするミーティング スペースに Microsoft Teams 会議室が既に展開されている場合、リソース アカウントには Microsoft Teams Rooms ライセンスが既に [割り当てされています](../rooms/rooms-licensing.md)。 このような場合は、パネルを展開するために、別個の Microsoft Teams Rooms Standard ライセンスを購入する必要が生じ得る必要があります。 管理者は、同じ領域の Microsoft Teams 会議室と同じ資格情報でパネル デバイスにサインインします。
>
>- ボード ルームや会議室など、複数の入り口がある大きなミーティング スペースの場合は、各入口に 1 つのパネル デバイスをマウントできます。 1 つのミーティング スペースに属する複数のパネルは、同じリソース アカウントを共有し、同じ資格情報でサインインします。 同じ領域のパネルごとに個別のリソース アカウントを作成する必要はありません。

> [!TIP]
> 実際の Teams パネルのインストールの前に、リソース アカウントを作成してください。
> Teams パネルリソース アカウントの名前付け規則の使用を検討してください。 Microsoft 365 リソース アカウントの表示名をわかりやすいわかりやすい名前にします。 Outlook または Teams の予定表で会議をスケジュールするときに、ユーザーが会議スペースを検索するときに表示される名前です。

### <a name="testing"></a>テスト

パネルを配置した後は、パネルをテストする必要があります。 Teams パネル [でサポートされる機能が、展開](#features-supported-by-teams-panels) されたデバイスで動作しているのを確認します。 コンピューター上の Teams または Outlook 365 を使用して、さまざまなタイム スロットに対して複数の会議を作成してみてください。 会議の詳細とスケジュールされた会議の空き時間情報がパネルに正しく表示されていることを確認します。 デバイスから直接 **使用可能** なミーティング スペースを予約できる場合は、[予約] ボタンを使用して確認してください。

## <a name="manage-teams-panels-in-your-organization"></a>組織内の Teams パネルを管理する

Teams パネル デバイスを管理するには、Microsoft Teams 管理センターの左側のナビゲーションで、[デバイス Teams] パネル  >  **に移動します**。 ここから、デバイス構成プロファイルの変更、更新の管理、デバイスの再起動、デバイス タグの追加と削除を行えます。 詳細については、「Teams でデバイス [を管理する」を参照してください](device-management.md)。

## <a name="next-steps"></a>次の手順

[Microsoft Teams パネル デバイスの使い方](use-teams-panels.md)

## <a name="see-also"></a>関連項目

[Teams パネルの Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[Teams パネルの使用を開始する](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Microsoft Teams パネル認定プログラムで認定されたデバイス](teams-ip-phones.md#currently-certified-teams-panels)