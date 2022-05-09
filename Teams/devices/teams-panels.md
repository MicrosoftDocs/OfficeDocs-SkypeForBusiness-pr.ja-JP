---
title: Microsoft Teams パネル
ms.author: serdars
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
ms.localizationpriority: medium
description: この記事では、Microsoft Teams パネルでサポートされている機能の概要と機能について説明します。
ms.openlocfilehash: b860b141cddddbb90ce9d28d7895cf385c77c0ff
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514742"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams パネル

Microsoft Teams パネルは、会議スペースのすぐ外側 (通常は入り口の横) に取り付けられるコンパクトなタッチスクリーン デバイスです。 Teams パネルを使用すると、場所と会議の詳細を一目で確認したり、その場で利用可能な会議スペースを予約したりできます。 リッチで大きなテキストと色分けされたインジケーターを使用すると、会議スペースの空き時間を遠くから確認できます。

Teams パネルは、Teamsまたは Outlook 365 予定表アプリケーションを使用してスケジュールされた会議の詳細を表示する専用のMicrosoft Teams デバイスです。 会議の詳細が目立つように表示されると、出席者は適切な会議スペース、適切なタイミング、適切な会議に参加していることを確認できます。

この記事では、Teams パネルの概要を説明し、組織内のTeams パネル デバイスの計画、提供、管理に役立ちます。

## <a name="features-supported-by-teams-panels"></a>Teams パネルでサポートされる機能

Teams パネルでは、次の機能がサポートされています。

- **会議スペースと会議の詳細の専用表示。** 会議スペースの場所や空き状況など、会議スペースに関する詳細をひと目で確認できます。 予約された会議スペースの場合は、会議のタイトル、会議のスケジュール、会議の開催者など、重要な会議の詳細を確認できます。
- **アドホック会議に使用できる会議スペースを予約します。** タッチスクリーン パネルを使用すると、アドホック会議のためにその場で利用可能な会議スペースを予約し、そのTeams会議に室内Microsoft Teams RoomsまたはSurface Hubデバイスから _参加_ できます。
- **空き領域の状態を示す色分けされたインジケーター。** 明るい LED とホーム画面のインジケーターを使用すると、会議スペースの空き時間を遠くから間近で確認できます。 緑色は会議スペースが使用可能であることを示し、必要に応じてパネル自体から直接予約できます。 赤または紫は、会議スペースが予約されていることを示します。
- **壁紙と予約状態インジケーターをカスタマイズします。** 管理者は、設定を使用してパネルの既定の外観を変更できます。 たとえば、管理者は背景の壁紙を変更したり、ビジー状態インジケーターの色を変更したりできます。
- **アクセシビリティ。** Teamsパネルには、ハイ コントラスト テキストなどのアクセシビリティ機能がいくつか用意されているため、だれでも簡単に使用できます。

これらの機能とその使用方法の詳細については、「[Microsoft Teams パネルを使用する](use-teams-panels.md)」を参照してください。

## <a name="partners-certified-for-teams-panels"></a>Teams パネル認定パートナー

Teams パネルで認定されたパートナーの詳細については、「[現在認定されているTeams パネル](teams-ip-phones.md#certified-teams-panels)」を参照してください。

## <a name="teams-panels-requirements"></a>Teams パネルの要件

パネル デバイスを展開するためのハードウェア、ソフトウェア、ネットワークの要件は、展開するパネル デバイスの種類によって異なる場合があります。 一連のデバイスに必要なものについては、OEM (Oem) のドキュメントを参照してください。

## <a name="license-requirement"></a>ライセンス要件

Teams パネルを使用するには、[ライセンスMicrosoft Teams Rooms Standard](../rooms/rooms-licensing.md)必要があります。

> [!Note]
> Teams パネルをインストールする会議スペースに既にMicrosoft Teams Rooms展開している場合は、Teams パネルを使用するための追加のライセンスは必要ありません。

## <a name="deploy-teams-panels-devices"></a>Teams パネル デバイスを展開する

Teams パネル デバイスの計画、展開、管理に関与している場合は、このセクションを参照してください。 このセクションは、Teams パネルのエンド ユーザーを対象としていません。

Teams パネル デバイスの展開は、次のタスクに分けることができます。

- [会議スペースインベントリと機能計画](#inventory-sites-and-meeting-spaces): Teams パネル デバイスを展開するための組織のサイトと会議スペースのインベントリを作成します。
- [調達](#procurement): 選択したデバイス パートナーからデバイスを調達します。  
- [サイトの準備状況](#site-readiness): 展開場所 (会議スペース) がデプロイ要件を満たしていることを確認します。
- [構成とデプロイ](#configuration-and-deployment): リソース アカウントを作成し、デバイスに割り当てます。

## <a name="inventory-sites-and-meeting-spaces"></a>インベントリ サイトと会議スペース

組織内の既存の予約可能な会議スペースのインベントリを取得します。 Teams パネルを展開するスコープ内のサイトと会議スペースを特定します。 施設やオーディオ ビジュアル チームと協力して、Teams パネル デバイスをインストールする場所と方法、およびパネルを取り付けるために追加のハードウェアが必要かどうかを判断します。

## <a name="procurement"></a>調達

Teams パネルを展開する範囲にある会議スペースの数に基づいて、Teams [パネルの認定を受けたパートナー](#partners-certified-for-teams-panels)からデバイスを調達します。 パートナーの Web サイトにアクセスして、デバイスと調達オプションの詳細を確認します。

組織内の会議スペースには、デバイスをインストールまたはマウントするためのハードウェア要件が異なる場合があります。 たとえば、デバイスをガラス、石材、ドライウォール、または木のパネルに取り付けるのに必要なハードウェアが同じでない可能性があります。 使用可能なマウント オプションについては、デバイス パートナーのドキュメントを参照してください。

## <a name="site-readiness"></a>サイトの準備

順序付けられたデバイスが組織に配信されている間、ネットワーク、施設、およびオーディオ ビジュアル チームと連携して、展開要件が満たされ、各サイトと会議スペースが電源とネットワークの面で準備ができていることを確認します。

Teams パネル サイトの推奨事項は次のとおりです。

- 専用リソース アカウント
- 電源 (パネルは一般に、Power over ethernet plus (PoE+) をサポートしています)。 デバイス固有の電源要件については、OEM のドキュメントを参照してください)。


物理的なインストールに関する考慮事項については、OEM のドキュメントを参照してください。また、ある場合は、デバイスをインストールしてマウントし、ケーブル接続を実行する前に、オーディオ ビジュアル チームのエクスペリエンスを使用してください。

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- テスト

### <a name="resource-account-provisioning"></a>リソース アカウントのプロビジョニング

すべてのTeams パネル デバイスには、Microsoft 365ルーム リソース アカウントが必要です。 リソース アカウントの資格情報を使用して、パネル デバイス上のアプリMicrosoft Teamsサインインします。

Teams パネルのMicrosoft 365 リソース アカウントを設定するには、[Microsoft Teams Rooms Standard ライセンス](#license-requirement)を購入することをお勧めします。 リソース アカウントを作成し、それにライセンスを割り当てる方法については、「[会議室と共有Teamsデバイスのリソース アカウントを作成](../rooms/with-office-365.md)する」を参照してください。

> [!NOTE]
>
>- パネルをインストールする会議スペース用に会議室リソース アカウントが既に設定されている場合は、同じルーム リソース アカウントを使用してパネル デバイスにサインインします。 ただし、会議室リソース アカウントをパネル リソース アカウントとして使用するには、ルーム リソース アカウントにMicrosoft Teams Rooms Standardライセンスが割り当てられていることを確認してください。
>
>- Teams パネルをインストールする会議スペースに既にMicrosoft Teams Roomsが展開されている場合は、パネルを展開するための別のライセンスを購入する必要はありません。 管理者は、同じ領域のMicrosoft Teams Roomsと同じ資格情報を使用してパネル デバイスにサインインします。
>
>- ボード ルームや会議室などの大規模な会議スペースに複数の入り口がある場合は、各入り口に 1 つのパネル デバイスを取り付けることができます。 1 つの会議スペースに属する複数のパネルが同じリソース アカウントを共有し、同じ資格情報でサインインします。 同じ領域に対してパネルごとに個別のリソース アカウントを作成する必要はありません。

> [!TIP]
> 実際のTeams パネルのインストールの前に、リソース アカウントを適切に作成することをお勧めします。
> Teams パネル リソース アカウントの名前付け規則の使用を検討してください。 Microsoft 365 リソース アカウントの表示名をわかりやすく説明します。 これらは、OutlookまたはTeams予定表で会議をスケジュールするときに、会議スペースを検索するときに表示される名前です。

### <a name="testing"></a>テスト

パネルをデプロイしたら、それらをテストする必要があります。 [Teams パネルでサポートされている機能](#features-supported-by-teams-panels)が、展開されたデバイスで動作していることを確認します。 コンピューター上の Teams または Outlook 365 を使用して、さまざまなタイム スロットに対して複数の会議を作成してみてください。 パネルに、スケジュールされた会議の会議の詳細と空き時間が正しく表示されているかどうかを確認します。 **[予約**] ボタンを使用して、デバイスから直接使用可能な会議スペースを予約できるかどうかを確認してください。

## <a name="manage-teams-panels-in-your-organization"></a>組織内のTeams パネルを管理する

Teams パネルのデバイスを管理するには、Microsoft Teams管理センターの左側のナビゲーションで **、Teams DevicesPanels** >  に移動 **します**。 ここから、デバイス構成プロファイルの変更、更新の管理、デバイスの再起動、デバイス タグの追加と削除などを行うことができます。 詳細については、「[Teamsでデバイスを管理する](device-management.md)」を参照してください。

## <a name="next-steps"></a>次のステップ

[Microsoft Teams パネル デバイスの使用方法](use-teams-panels.md)

## <a name="see-also"></a>関連項目

[Teams パネルでブログをMicrosoft Teamsする](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[Teams パネルを使用した概要](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Teams パネル マーケットプレース](https://office.com/teamsdevices)

[Microsoft Teams パネル認定プログラムで認定されたデバイス](teams-ip-phones.md#certified-teams-panels)
