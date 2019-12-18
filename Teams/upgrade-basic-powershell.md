---
title: PowerShell の基本的なアップグレード | Microsoft Teams | アップグレード相互運用ポリシーの付与
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 管理センターがテナントで起動していない場合、Teams にアップグレードするための一時的な作業
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397cabcbba35c153d234bc4355d12e4eb44b5c57
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435091"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Skype for Business Online から Microsoft Teams へのユーザーのアップグレード

> [!Note]
> この記事で説明するコマンドは、「[アップグレードの基本](https://aka.ms/UpgradeBasic)」チェックリストの一部として使用するように設計されています。

アップグレードの技術的な移行の側面では、Skype for Business が Teams にアップグレードされることをユーザーに通知し、**Teams only** モードに移行します。 これらの手順を実行するには、Skype for Business のリモート Windows PowerShell セッションを使用するか、Microsoft Teams 管理センターを使用します。

アップグレード ツールは [Microsoft Teams 管理センター](manage-teams-skypeforbusiness-admin-center.md)で積極的に展開しており、すぐにテナントで使用可能になる予定です。 使用可能になり次第、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」でユーザーの移行に関する情報を見つけることができます。

今日アップグレードする準備ができている場合は、次の表にリストされている [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) コマンドを使用できます。

| アップグレードの基本手順 ＃ | モード | PowerShell コマンド |
|---|---|---|
| [5](upgrade-basic.md#step-5) | アイランド + Skype for Business ユーザーへの通知<br>(ユーザが現在**アイランド** モード (既定) の場合、このコマンドを使用する) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(たとえば、$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business のみ + Skype for Business ユーザーへの通知 <br>(ユーザが現在 **Skype for Business のみ** モードの場合、このコマンドを使用する) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams のみ | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
