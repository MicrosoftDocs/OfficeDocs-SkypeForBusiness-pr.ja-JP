---
title: Microsoft Teams パネルでのチェックインと会議室のリリース
ms.author: dstrome
author: dstrome
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
description: この記事では、チェックインと会議室のリリースTeamsパネル デバイスを有効にする方法に関するガイダンスを提供します。
ms.openlocfilehash: a1fc01b349a2189ab2f5ca09ff6b856338fbcdbb
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761279"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Microsoft Teams パネルでのチェックインと会議室のリリース

チェックインと会議室のリリースが有効になっている場合、ユーザーは会議の開始時に予約した会議室のTeams パネルでチェックインします。 ユーザーが会議の開始時刻の後に一定の時間内にチェックインしなかった場合、会議室は会議出席依頼を拒否し、会議の開催者にキャンセル メッセージを送信し、他のユーザーが予約できる会議室になります。  

## <a name="requirements"></a>要件 

この機能は、スタンドアロンのTeams パネルデプロイで使用できます。 チェックイン通知などの追加機能については、Teams パネルとAndroidのTeams Roomsをアプリ バージョン 1449/1.0.96.2022011305 以降とペアリングすることもできます。  

## <a name="enable-check-in-and-room-release"></a>チェックインと会議室のリリースを有効にする 

チェックインと会議室のリリースは既定でオフになっています。 これをオンにするには、  

1. Teams パネルで、管理者資格情報を使用してサインインします。  

2. **[設定 >デバイス設定] > 管理設定> Teams管理者設定>会議** に移動します。

3. 誰もチェックインしない場合は、リリース ルームをオンにします。

4. ユーザーが会議室をリリースする前にチェックインする必要がある時間を調整するには、[ **リリース後にリリース:]** に移動し、ドロップダウンからオプションを選択します。  

TeamsパネルがAndroidのTeamsルームとペアリングされている場合、ユーザーはTeams会議室で会議に参加していることを確認できます。  

## <a name="turn-on-check-in-notifications"></a>チェックイン通知を有効にする

> [!NOTE]
> この機能は現在、AndroidのTeamsルームとペアリングされているTeams パネルでのみ使用できます。 Teams パネルとTeamsルームは、同じリソース アカウントにサインインする必要があります。 詳細については、「[AndroidのMicrosoft Teams ルームとTeams パネルをペアリング](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)する」を参照してください。  

チェックイン通知は、会議が予約済みの時間帯を過ぎても続く場合に送信されます。 次の会議のユーザーがチェックインすると、スケジュールされた会議の開始時刻に会議室の前面に通知が表示され、前の会議参加者が予約が終了し、ユーザーが空きを待っていることがわかります。  

チェックイン通知を有効にするには、  

1. Teams パネルで、管理者資格情報を使用してサインインします。 

2. **[設定 >デバイス設定] > 管理設定> Teams管理者設定>会議** に移動します。

3. **チェックイン** に移動し、[チェックイン通知の **送信**] をオンにします。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams パネルの使用方法](use-teams-panels.md)

- [Microsoft Teams パネル](teams-panels.md)
