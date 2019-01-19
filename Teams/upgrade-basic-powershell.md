---
title: 基本的なアップグレードの PowerShell |マイクロソフトのチーム。相互運用機能のポリシーを与えるアップグレード
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 管理センターは、テナントに点灯していない場合は、チームにアップグレードするための暫定的な
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 753a79bb8138577b5f97666b5b0081520bd386fe
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349242"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>ユーザーをアップグレードする、Skype のオンライン ビジネスのマイクロソフトのチームに

> [!Note]
> この資料で説明するコマンドは、[基本のアップグレード](https://aka.ms/UpgradeBasic)のチェックリストの一部として使用するために設計されています。

アップグレードの移行の技術的な側面、ビジネス用の Skype はチームへのアップグレード、**チームのみ**のモードに移動して、ユーザーに通知することが必要になります。 ビジネス リモートの Windows PowerShell セッションまたはマイクロソフト チーム & ビジネス管理センターの Skype、Skype 経由でこれらの手順を実現できます。

[マイクロソフトのチーム & ビジネス管理センターの Skype](manage-teams-skypeforbusiness-admin-center.md)では、ツールのアップグレードを積極的に展開してと、テナントですぐに利用可能な場合があります。 使用可能になると[の共存を設定](https://aka.ms/SkypeToTeams-SetCoexistence)および設定をアップグレードするユーザーの移行に関する情報が表示されます。

今すぐアップグレードする準備が整ったら、 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)コマンドを次の表に記載されているを使用することができます。

| アップグレードの基本的なステップ # | モード | PowerShell コマンド |
|---|---|---|
| [5](upgrade-basic.md#step-5) | 諸島 +、Skype をビジネス ユーザーに通知<br>(**諸島**モード (既定値) でユーザーがいる場合は、このコマンドを使用して) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(たとえば、$SipAddress = 'TestUser@contoso.com')*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | ビジネスのみの Skype、Skype をビジネス ユーザーに通知する + <br>( **Skype**ビジネスのみのモードでユーザーがいる場合は、このコマンドを使用します) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | チームのみ | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |