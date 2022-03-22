---
title: パネル上のチェックインとルーム Microsoft Teamsリリース
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: この記事では、パネル デバイスでチェックインとルーム リリースを有効にする方法Teams示します。
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689102"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>パネル上のチェックインとルーム Microsoft Teamsリリース

チェックインと会議室の解放が有効になっている場合、ユーザーは会議のTeamsに予約した会議室のパネルにチェックインします。 ユーザーが会議の開始時刻から一定の時間内にチェックインしない場合、会議室は会議出席を拒否し、会議の開催者にキャンセル メッセージを送信し、会議室は他のユーザーが予約できます。  

## <a name="requirements"></a>要件 

この機能は、スタンドアロンのパネル デプロイTeams使用できます。 アプリ バージョン 1449/1.0.96.2022011305 以降で Teams パネルと Teams Rooms on Android をペアリングして、チェックイン通知のような追加機能を利用することもできます。  

## <a name="enable-check-in-and-room-release"></a>チェックインとルーム リリースを有効にする 

チェックインとルーム リリースは既定でオフになっています。 オンにする場合は、  

1. [Teams] パネルで、管理者の資格情報を使用してサインインします。  

2. [デバイスと **設定 >管理者] 設定 >パネル 設定 >会議] 設定 >します**。

3. 誰も確認できない場合は、リリース ルームを有効にしてください。

4. ルームが解放される前にユーザーがチェックインする必要がある時間を調整するには、[リリース後: ] に移動し、ドロップダウンからオプションを選択します。  

パネルTeams Android の Teams Room とペアリングされている場合、ユーザーは Teams Room で会議に参加してチェックインできます。  

## <a name="turn-on-check-in-notifications"></a>チェックイン通知を有効にする

> [!NOTE]
> 現在、この機能は、Android Teams Room とペアにされているTeamsでのみ使用できます。 このTeamsとTeams、同じリソース アカウントにサインインする必要があります。 詳細[については、「Teams パネルと Android Microsoft Teamsルーム](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)をペアリングする」を参照してください。  

チェックイン通知は、会議が予約されたタイム スロットを過ぎた後に送信されます。 次の会議のユーザーが入室すると、スケジュールされた会議の開始時刻に通知が会議室の前面に表示され、前の会議の参加者に予約が終了し、参加者が空き時間を待つことを通知します。  

チェックイン通知を有効にするには、  

1. [Teams] パネルで、管理者の資格情報を使用してサインインします。 

2. [デバイスと **設定 >管理者] 設定 >パネル 設定 >会議] 設定 >します**。

3. [チェックイン **] に移動し** 、[チェックイン通知 **の送信] をオンにします**。

## <a name="related-topics"></a>関連項目

- [パネルのMicrosoft Teams方法](use-teams-panels.md)

- [Microsoft Teams パネル](teams-panels.md)