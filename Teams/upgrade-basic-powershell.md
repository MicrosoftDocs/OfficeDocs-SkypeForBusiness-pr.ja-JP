---
title: 基本的なアップグレード PowerShell |Microsoft Teams |アップグレードの相互運用ポリシーを付与する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: テナントで管理センターが使用されていない場合に、Teams にアップグレードするための Stopgap
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435091"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>ユーザーを Skype for Business Online から Microsoft Teams にアップグレードする

> [!Note]
> この記事で説明しているコマンドは、[アップグレードの基本的な](https://aka.ms/UpgradeBasic)チェックリストの一部として使用するように設計されています。

アップグレードの技術的な移行には、Skype for Business が Teams にアップグレードされることをユーザーに通知し、それを**チーム専用**モードに移行する必要があります。 これらの手順は、Skype for Business リモート Windows PowerShell セッションまたは Microsoft Teams 管理センターを使用して行うことができます。

[Microsoft Teams 管理センター](manage-teams-skypeforbusiness-admin-center.md)でアップグレードツールを積極的にロールアウトしています。この機能は、お使いのテナントから間もなく利用可能になります。 この機能が利用可能になったら、ユーザーを移行するための情報を、[共存とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)で確認できます。

今すぐアップグレードする準備ができたら、次の表に示す[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)コマンドを使用できます。

| アップグレードの基本手順# | Mode | PowerShell コマンド |
|---|---|---|
| [5](upgrade-basic.md#step-5) | 諸島 + Skype for Business ユーザーに通知する<br>(現在、ユーザーが現在**諸島**モード (既定) である場合は、このコマンドを使用します)。 | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*($SipAddress = ' TestUser@contoso.com ' など)* |
| [5](upgrade-basic.md#step-5) | Skype for Business で Skype for business のユーザーに通知する <br>(現在、ユーザーが**Skype For business のみ**のモードである場合は、このコマンドを使用) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Only | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
