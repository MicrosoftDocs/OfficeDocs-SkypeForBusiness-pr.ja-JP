---
title: Teams と連動するように Skype 会議アプリを構成する
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: 管理者は、Microsoft Teams 管理センターを使用して、Teams と連携するように Skype 会議アプリを構成することができます。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29887ee89c8db36e6d5116118e0ec4fbc2a3e0ff
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856446"
---
# <a name="configure-the-skype-meetings-app-to-work-with-teams"></a>Teams と連動するように Skype 会議アプリを構成する

ユーザーが Microsoft Teams にアップグレードされた後、管理者は、Microsoft Teams 管理センターを使用して、ユーザーが Skype for Business 会議に参加するために使用する優先アプリを指定できます。

Skype 会議アプリを優先アプリとして指定するには、次の操作を行います。

1. Microsoft Teams 管理センターにサインインする。
2. 左側のウィンドウで、**[組織全体の設定]** の下にある **[Teams のアップグレード]** を選択します。
3. Teams のアップグレード ページの **[アプリの環境設定]** で、**[Skype for Business 会議に参加するユーザー向けの優先アプリ]** ドロップダウンリストから、**[Skype 会議アプリ]** を選択します。

    ![[Skype for Business 会議に参加するユーザー向けの優先アプリ] を選択する](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a>既知の制限

Teams と Skype 会議アプリを使うユーザーには、次の制限があります。

- ユーザーがビデオ デバイスを変更することはできません。
- ユーザーが Teams にアップグレードした後、ユーザーが Skype 会議アプリを使用して会議を行っているときに Teams で通話を受信した場合、Skype 会議アプリの会議は保留にされません。 代わりに、ユーザーは両方の呼び出しに接続されます。

## <a name="more-information"></a>詳細情報

- [Skype 会議アプリ (Skype for Business Web アプリ) とは](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- [Skype 会議アプリの最小ネットワーク要件](/previous-versions/office/communications/mt845808(v=ocs.16))