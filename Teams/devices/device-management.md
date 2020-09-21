---
title: Microsoft Teams でのデバイスの管理
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 組織内の Teams で使用されているデバイスを管理する方法について説明します。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac6c0b503266a83033a72940ea6572feeaffaf5
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47964794"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Microsoft Teams でのデバイスの管理

Microsoft Teams 管理センターから組織の Microsoft Teams で使用されているデバイスを管理することができます。 組織のデバイスのインベントリを表示して管理できます。また、デバイスの診断の更新、再起動、監視などのタスクを実行することができます。 構成プロファイルを作成して、1つのデバイスまたはデバイスのグループに割り当てることもできます。

デバイスの構成の変更、デバイスの再起動、更新プログラムの管理、デバイスと周辺機器の正常性の表示など、デバイスを管理するには、次の Microsoft 365 管理者ロールのいずれかを割り当てる必要があります。

- Microsoft 365 グローバル管理者
- Teams サービス管理者
- Teams デバイス管理者

Teams の管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。

## <a name="what-devices-can-you-manage"></a>どのデバイスを管理できますか?

Teams で認定され、登録されているすべてのデバイスを管理することができます。 ユーザーがデバイス上のチームに初めてサインインしたときに、デバイスが自動的に登録されます。 管理可能なデバイスの一覧については、以下を参照してください。

- [Microsoft Teams ルーム](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [電話会議](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [卓上電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [コラボレーションバー](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

これらのデバイスは、 [Microsoft Teams 管理センター](https://admin.teams.microsoft.com) で管理されており、左側のナビゲーションの [ **デバイス**] の下にそれぞれのセクションがあります。 これにより、各種類のデバイスを個別に管理することができます。

## <a name="manage-teams-rooms-devices"></a>Teams 室のデバイスを管理する

Teams 管理センターを使用して、組織全体のチームルームデバイスを表示し、リモートで管理することができます。 Teams 管理センターでは、どのデバイスが稼働していて、どのデバイスが正常に動作しているかをひとめで確認して、デバイスの正常性、会議のパフォーマンス、通話品質、周辺機器に関する詳細情報を表示するために、特定のデバイスに集中することができます。 

ここでは、Teams 室のデバイスを管理するためにできることについて説明します。 Teams 室のデバイスは、 [Microsoft Teams 管理センター](https://admin.teams.microsoft.com)の [**デバイス**  >  **Teams ルーム**] にあります。

Teams 室のデバイスを管理する方法の詳細については、「 [Microsoft Teams のルームを管理](../rooms/rooms-manage.md)する」を参照してください。

| 操作方法 | 操作|
|---------------|--------|
| 1つまたは複数のデバイスの設定を変更する | [ **設定の編集**] > 1 つ以上のデバイスを選択します。 複数のデバイスを選択すると、変更した値によって、選択したすべてのデバイスの値が置き換えられます。 |
| デバイスを再起動する | 1つ以上のデバイスを選択し > **再起動**します。 デバイスを再起動する場合は、デバイスをすぐに再起動するか、[ **再起動のスケジュール** ] を選択して特定の日時にデバイスを再起動するかを選ぶことができます。 選択した日付と時刻は、再起動されるデバイスに対してローカルになります。|
| 会議のアクティビティを表示する | デバイス名を選択して、[デバイスの詳細 > **アクティビティ**] を開きます。 [ **アクティビティ** ] タブを開くと、デバイスが参加しているすべての会議が表示されます。 この概要ビューには、会議の開始時刻、参加者の数、再生時間、全体的な通話品質が表示されます。|
| 会議の詳細を表示する |  デバイス名を選択して [デバイスの詳細 > **アクティビティ** を開く > 会議を選択します。 会議の詳細を開くと、会議の参加者全員、通話中の会議の時間、チームのセッションの種類、個々の通話音質を確認できます。 参加者の通話に関する技術情報を表示するには、参加者の通話開始時刻を選択します。|

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>Teams で電話とコラボレーションバーを管理する

Teams 管理センターでは、組織のチームに登録されている携帯電話とコラボレーションバーを表示して管理することができます。 各デバイスに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、操作、最後の表示、履歴が含まれます。 目的に合った情報が表示されるように、ビューをカスタマイズすることができます。

スマートフォンとコラボレーションバーは、サインアップしている場合、Microsoft Intune に自動的に登録されます。 デバイスが登録されると、デバイスのコンプライアンスが確認され、条件付きアクセスポリシーがデバイスに適用されます。

組織で固定電話やコラボレーションバーを管理する方法の例を次に示します。  

|操作方法  |操作 |
|---------|---------|
| デバイスの情報を変更する               | [ **編集**] > デバイスを選択します。 デバイス名、アセットタグ、メモの追加などの詳細を編集できます。     |
| ソフトウェアの更新を管理する                 | **更新**> デバイスを選択します。 デバイスで利用可能なソフトウェアとファームウェアの更新プログラムの一覧を表示し、インストールする更新プログラムを選ぶことができます。 デバイスの更新の詳細については、「 [Microsoft Teams デバイスをリモートで更新](remote-update.md)する」を参照してください。   |
| 構成ポリシーを割り当てる、または変更する | [ **構成の割り当て**] > 1 つ以上のデバイスを選択します。                                                                                                                                                                                                                   |
| デバイスタグを追加または削除する               | 1つ以上のデバイスを選択して、 **タグ > 管理**します。 デバイスタグの詳細については、「 [Microsoft Teams デバイスの管理とフィルター処理](manage-device-tags.md)を行う」を参照してください。                                                                                                      |
| デバイスを再起動する                         | 1つ以上のデバイスを選択し > **再起動**します。                                                                                                                                                                                                                                |
| デバイスタグを使ってデバイスをフィルター処理する        | [フィルター] アイコンを選択し、[ **タグ** ] フィールドを選択し、フィルター処理するデバイスタグを指定して、[ **適用**] を選択します。 Device タグを使用したデバイスのフィルター処理の詳細については、「 [フィルターを使用して特定のタグでデバイスを返す](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)」を参照してください。|
| デバイス履歴の表示                     | デバイス > の **履歴**を選択します。 デバイスの更新履歴を表示できます。                                                                                                                                                                                |
| 診断の表示                        | **診断**> デバイスを選択します。                                                                                                                                                                                                                            |


### <a name="use-configuration-profiles-in-teams"></a>Teams で構成プロファイルを使用する

構成プロファイルを使用して、組織内のチーム電話とコラボレーションバーの設定と機能を管理します。 構成プロファイルを作成またはアップロードして、有効または無効にする設定や機能を含め、デバイスまたはデバイスのグループにプロファイルを割り当てることができます。 

#### <a name="create-a-configuration-profile"></a>構成プロファイルを作成する

1. 左側のナビゲーションで、[**デバイス**  >  **構成プロファイル**] に移動します。
2. **[追加]** をクリックします。
3. プロファイルの名前を入力し、必要に応じてわかりやすい説明を追加します。
4. プロファイルに必要な設定を指定し、[ **保存**] をクリックします。

#### <a name="assign-a-configuration-profile"></a>構成プロファイルを割り当てる

1. 左側のナビゲーションで、[**デバイス**  >  **構成プロファイル**] に移動します。
2. 割り当てる **構成プロファイル** を選び、[ **デバイスへの割り当て**] をクリックします。  
3. [ **構成プロファイルへのデバイスの割り当て** ] ウィンドウで、割り当てるデバイスを検索して選びます。
4. [**保存**] をクリックします。

