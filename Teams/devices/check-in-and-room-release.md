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
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: この記事では、チェックインと会議室リリースの Teams パネル デバイスを有効にする方法に関するガイダンスを提供します。
ms.openlocfilehash: d5998049faf1e3c8c25b3e49470291bb20f97eea
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801858"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Microsoft Teams パネルでのチェックインと会議室のリリース

チェックインと会議室のリリースが有効になっている場合、ユーザーは会議の開始時に予約した会議室の Teams パネルでチェックインします。 ユーザーが会議の開始時刻から一定時間内にチェックインしない場合、ミーティング ルームは会議出席依頼を拒否し、会議の開催者にキャンセル メッセージを送信し、他のユーザーが予約できるように会議室を使用できるようになります。  

## <a name="requirements"></a>要件 

この機能は、スタンドアロンのTeams パネルデプロイで使用できます。 また、Android のTeams Roomsと Teams パネルをアプリ バージョン 1449/1.0.96.2022011305 以降とペアリングして、チェックイン通知などの追加機能を提供することもできます。

Teams パネルに関連付けられている共有メールボックスには、この機能が正しく機能するために適切なタイム ゾーンが設定されている必要があります。 共有メールボックスのタイム ゾーンを設定する方法については、「[Outlook on the webの共有メールボックスのタイム ゾーン設定](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting)」を参照してください。

## <a name="enable-check-in-and-room-release"></a>チェックインと部屋の解放を有効にする 

チェックインと部屋の解放は既定でオフになっています。 オンにするには、  

1. Teams パネルで、管理者の資格情報を使用してサインインします。  

2. [**設定] > [デバイスの設定] > 管理 [設定] > [Teams 管理者設定] > [会議] に移動します**。

3. **誰もチェックインしない場合は、リリース ルームを** オンにします。

4. ルームが解放される前にユーザーがチェックインする必要がある時間を調整するには、[ **リリース後** : ] に移動し、ドロップダウンからオプションを選択します。  

Teams パネルが Android 上の Teams Room とペアリングされている場合、ユーザーは Teams 会議室で会議に参加していることを確認できます。  

## <a name="turn-on-check-in-notifications"></a>チェックイン通知を有効にする

> [!NOTE]
> この機能は現在、Android 上の Teams ルームとペアになっている Teams パネルでのみ使用できます。 Teams パネルと Teams ルームは、同じリソース アカウントにサインインする必要があります。 詳細については、「[Android 上の Microsoft Teams Room とTeams パネルをペアリング](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)する」を参照してください。  

チェックイン通知は、会議が予約されたタイム スロットを超えて続行しているときに送信されます。 次の会議のユーザーがチェックインすると、スケジュールされた会議の開始時刻に会議室ディスプレイの前面に通知が表示され、前の会議参加者に予約が終了し、ユーザーがスペースを待っていることがわかります。  

チェックイン通知を有効にするには、  

1. Teams パネルで、管理者の資格情報を使用してサインインします。 

2. [**設定] > [デバイスの設定] > 管理 [設定] > [Teams 管理者設定] > [会議] に移動します**。

3. [ **チェックイン** ] に移動し、[ **チェックイン通知の送信]** をオンにします。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams パネルの使用方法](use-teams-panels.md)

- [Microsoft Teams パネル](teams-panels.md)
