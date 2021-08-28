---
title: Microsoft Teams Rooms プレミアムマネージド サービスに Teams Rooms デバイスを登録する
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 管理されたサービスを使用して、Microsoft Teams Rooms アカウントを Microsoft Teamsするプレミアムについて説明します。
f1keywords: ''
ms.openlocfilehash: a6aa59a798e06c407c1bbde6734ec9ab3ecedcd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58637022"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>管理対象サービスの Microsoft Teams Rooms プレミアムデバイスを登録する

Teams Rooms プレミアム マネージド サービスに Microsoft Teams Rooms デバイスを登録するには、1 人のユーザーを管理対象サービス管理者に割り当て、そのユーザーを使用して登録手順を完了する必要があります。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>管理対象サービス管理者ロールにユーザーを割り当てる

マネージド サービス管理者ロールにユーザーを割り当てるには、次の手順を実行します。

1. Teams [Rooms](https://portal.rooms.microsoft.com/)プレミアムにログインする場合と同じ管理者特権で Microsoft 365 管理センター。
2. [ロール]  >  **設定設定**  >  **し、[** マネージド サービス管理者]**を選択します**。
3. [ **管理対象サービス管理者] で、[** 割り当て] タブ **を選択** し、[追加] を **選択します**。
4. ウィザードに従って割り当ての名前を付け、追加する必要があるユーザーを選択します。 課題は、すべてのルームとルーム グループに適用されます。
5. 割り当てウィザードの最後で、[割り当ての追加] **を選択します**。

マネージド サービス管理者ロールが割り当てられているユーザーは、Teams Rooms プレミアムマネージド サービス ポータルの毎日の管理と監視を担当します。

管理対象サービス管理者ロールにユーザーを割り当てた後、[デバイスの登録][](#enroll-a-teams-rooms-device)セクションに進み、Teams Rooms デバイスをマネージド サービス ポータルに追加します。

## <a name="enroll-a-teams-rooms-device"></a>会議室デバイスTeams登録する

管理対象サービスの Teams Rooms にデバイスプレミアムするには、次の手順を実行します。

1. マネージド サービス管理者ロール[Teams](https://portal.rooms.microsoft.com/)割りプレミアムを使用して、プレミアム Rooms ポータルにログインします。
2. を選択 **します。** アイコンを選び、ヘルプ メニューを起動します。 ヘルプ メニューには、詳細な [登録手順を](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) 含むインストール ガイドが含まれています。

    1. インストール ガイド **の前提条件に関** するセクションを確認します。 [通信に必要な URL]ボックスの一覧に表示されている URL が、ファイアウォールのトラフィック許可リストに追加されます。
    2. デバイスでトラステッド プラットフォーム モジュール **(TPM)** 設定機能を有効にするには、「TPM モジュールの有効化」セクションの手順に従います。
    3. プロキシ ゲートウェイがある場合は、設定 の追加に関するセクションの手順に従って、プロキシ ゲートウェイを使用するデバイスを構成します。
    4. [プロセス] セクションの **指示に** 従って監視エージェント ソフトウェアをインストールし、デバイスに自己登録キーを構成します。

3. 監視エージェントと一意の XML キーがデバイスで構成された後、[会議室] > [状態] > に移動し、[登録]**を選択****します**。

    > [!NOTE]
    > 管理Teams管理者がポータルを使用してデバイスを登録するまで、Teams Rooms デバイスはオンボード状態のままです。

## <a name="link-to-installation-guide"></a>インストール ガイドへのリンク

[ **ヘルプ]** メニューにはインストール ガイドへのリンク [が表示され](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) 、次の情報が表示されます。

- ルーム テレメトリをマネージド サービスに送信するために使用を許可する必要がある URL に関する手順。
- Microsoft Teams Rooms プレミアム監視エージェントと一意の XML キーをマネージド サービスにデバイスを登録する一部として適用する手順。
- トラブルシューティングの手順。
