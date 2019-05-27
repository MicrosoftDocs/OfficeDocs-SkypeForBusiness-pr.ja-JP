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
ms.openlocfilehash: 38fd76bff3309655cb7d2fa1f0acf18559f15220
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433368"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Microsoft Teams での保持ポリシーの既知の問題

現在追跡および調査されている Teams の保持ポリシーに関する既知の問題を以下に示します。

- Teams のチャネル メッセージの場所の行にある [チームの選択] の下で、Teams ではない Office 365 グループが表示される場合があります。 この問題は、今後解決される予定です。

- Teams のチャットの場所の行にある [ユーザーの選択] の下で、ゲストやメールボックスのユーザーでない人が表示される場合があります。 保持ポリシーはゲストのために設定されるものではありませんので、現在これらの表示をリストから削除するよう取り組んでいます。

- Exchange Life Cycle アシスタント (ELC) は毎日実行しますが、その SLA は 7 日間です。 このため、60 日以上経過したアイテムを削除する Teams の保持ポリシーを設定している場合、それらのアイテムは最大 67 日間保持される可能性があります。 これは新しい状況ではなく、Exchange の様式によるものです。 多くの場合において、遅延はありません。


| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次の手順を示すアイコン](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |次のステップ         |必須のセキュリティとコンプライアンスの機能を文書化します。         |
