---
title: Microsoft Teams での保持ポリシーの既知の問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Microsoft Teams の保持ポリシーに関する既知の問題の最新リストです。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dca7decd2c3c051c0d56a14e2a2d1485b777f92e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517064"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Microsoft Teams での保持ポリシーの既知の問題

現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。

- Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams. This will be addressed in the future.

- Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users. Retention policies are not meant to be set for guests, and we are working to remove these from the list.

- Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days. As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days. This isn't a new situation - it follows the Exchange model. Of course, in most cases, there is no delay.


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |次のステップ         |必須のセキュリティとコンプライアンスの機能を文書化します。         |
