---
title: 会議をTeamsする
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 新しい会議のストリーミングを設定および管理するTeamsします。
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127547"
---
# <a name="stream-teams-meetings"></a>会議をTeamsする

この記事は、会議のストリーミングを設定Teamsします。

## <a name="what-is-streaming-and-how-does-it-work"></a>ストリーミングとは何ですか?また、どのように動作しますか?

ストリーミングを使用すると、組織はリーチを拡大し、会議の出席者に会議のオプションを増やします。 ストリーミングを有効にした場合、開催者は Real-Time メッセージング プロトコル (RTMP) URL とキーを Teams の組み込みのカスタム ストリーミング アプリに提供することで、会議やウェビナーを外部エンドポイントにストリーミングできます。

> [!NOTE]
> ライブ イベントをストリーミングできない。

## <a name="set-up-streaming-with-powershell"></a>PowerShell を使用してストリーミングを設定する

PowerShell を使用して、ストリーミング用に組織を設定できます。 現時点では、このポリシーは管理センター Teamsできません。 ユーザーごとのポリシーは、ライブ ストリーミングを有効に **できるユーザー** を指定するために使用されます。 規定ではオフになっています。

**Set-CsTeamsMeetingPolicy** コマンドレットの Windows PowerShell属性を使用して、ストリーミングを設定できます。 コマンドレットの詳細については [、Set-CsTeamsMeetingPolicy に関するページを参照してください](/powershell/module/skype/set-csteamsmeetingpolicy)。

- LiveStreamingMode

1 人または複数のユーザーのストリーミング機能を有効にする場合は **、[LiveStreamingMode]** を [有効] に設定します。

> [!IMPORTANT]
> 開催者がウェビナーをストリーミングするには、会議の登録を有効にする必要があります。 詳細については、「ウェビナーを [設定する」を参照してください](set-up-webinars.md)。

### <a name="assign-the-policy"></a>ポリシーを割り当てる

PowerShell でポリシーを割り当てる方法の詳細については、「PowerShell でポリシーを割り当てる[」を参照Teams。](policy-assignment-overview.md)

## <a name="related-topics"></a>関連項目

- [Teams でポリシーを割り当Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [クイック スタート - 会議、ウェビナー、ライブ イベント](quick-start-meetings-live-events.md)