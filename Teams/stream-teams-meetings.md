---
title: 会議Teamsストリーミングする
author: mkbond007
ms.author: mabond
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
description: Teams会議のストリーミングを設定および管理する方法について説明します。
ms.openlocfilehash: 352a0c2e7a0584640e466b5e46456906e4912d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646346"
---
# <a name="stream-teams-meetings"></a>会議Teamsストリーミングする

この記事は、Teams会議のストリーミングを設定する際に役立ちます。

## <a name="what-is-streaming-and-how-does-it-work"></a>ストリーミングとは何か、どのように動作しますか?

ストリーミングを使用すると、組織はリーチを拡大し、会議出席者に会議オプションを追加できます。 ストリーミングを有効にすると、開催者は、Real-Time メッセージング プロトコル (RTMP) の URL と、組み込みのカスタム ストリーミング アプリのキーをTeamsに提供することで、会議やウェビナーを外部エンドポイントにストリーミングできます。

> [!NOTE]
> ライブ イベントをストリーミングすることはできません。

## <a name="set-up-streaming-with-powershell"></a>PowerShell を使用してストリーミングを設定する

PowerShell を使用してストリーミング用に組織を設定できます。 現時点では、このポリシーはTeams管理センターでは使用できません。 ユーザーごとのポリシーは、ライブ ストリーミングを有効にできる **ユーザー** を指定するために使用されます。 規定ではオフになっています。

Windows PowerShell **Set-CsTeamsMeetingPolicy** コマンドレット内で次の属性を使用して、ストリーミングを設定できます。 コマンドレットの詳細については、「 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

- LiveStreamingMode

**LiveStreamingMode** を **有効** に設定して、1 人以上のユーザーのストリーミング機能を有効にします。

> [!IMPORTANT]
> 開催者がウェビナーをストリーミングするには、会議の登録を有効にする必要があります。 詳細については、「 [ウェビナーを設定する](set-up-webinars.md)」を参照してください。

### <a name="assign-the-policy"></a>ポリシーを割り当てる

PowerShell でポリシーを割り当てる方法の詳細については、「[Teamsでポリシーを割り当てる](policy-assignment-overview.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [Teams でポリシーを割り当てる](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [クイック スタート - 会議、ウェビナー、ライブ イベント](quick-start-meetings-live-events.md)