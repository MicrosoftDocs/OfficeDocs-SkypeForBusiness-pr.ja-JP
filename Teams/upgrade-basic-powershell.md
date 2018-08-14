---
title: 基本の PowerShell コマンド - マイクロソフトのチームをアップグレードします。
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 管理センターは、テナントに点灯していない場合は、チームにアップグレードするための暫定的な
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b65cd7a7b9ef91194b2045193a98672bfd25326
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001720"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>ユーザーをアップグレードする、Skype のオンライン ビジネスのマイクロソフトのチームに

> [!Note]
> この資料で説明するコマンドは、[基本のアップグレード](https://aka.ms/UpgradeBasic)のチェックリストの一部として使用するために設計されています。

アップグレードの移行の技術的な側面、ビジネス用の Skype はチームへのアップグレード、**チームのみ**のモードに移動して、ユーザーに通知することが必要になります。 リモートの Windows PowerShell セッションをビジネス用またはマイクロソフトのチームとビジネス管理センターの Skype、Skype 経由でこれらの手順を実現できます。 
 
[マイクロソフトのチームとビジネス管理センターの Skype](manage-teams-skypeforbusiness-admin-center.md)で、ツールのアップグレードを積極的に展開してと、テナントですぐに利用可能な場合があります。 使用可能になると[の共存を設定](https://aka.ms/SkypeToTeams-SetCoexistence)および設定をアップグレードするユーザーの移行に関する情報が表示されます。 
 
今すぐアップグレードする準備が整ったら、 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)コマンドを次の表に記載されているを使用することができます。 
 
 |アップグレードの基本的なステップ # | モード | PowerShell コマンド |
|-------|--------|------|
| [5](upgrade-basic.md#step-5) |諸島 +、Skype をビジネス ユーザーに通知<br>(**諸島**モード (既定値) でユーザーがいる場合は、このコマンドを使用して) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>_(たとえば、$SipAddress = 'TestUser@contoso.com')_<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5)  | ビジネスのみの Skype、Skype をビジネス ユーザーに通知する + <br>( **Skype**ビジネスのみのモードでユーザーがいる場合は、このコマンドを使用します) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | チームのみ | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


