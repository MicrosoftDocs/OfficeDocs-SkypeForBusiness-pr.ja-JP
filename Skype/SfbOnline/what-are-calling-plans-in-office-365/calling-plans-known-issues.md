---
title: "プランの既知の問題を呼び出す"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: "(PSTN 通話) Office 365 とは何ができる通話プランの既知の問題について説明します。 "
ms.openlocfilehash: cb572c9de92cd53384c07c4e48779598ca73bb8c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="calling-plans-known-issues"></a>プランの既知の問題を呼び出す

通話プランの Office 365 では、skype for Business Online に表示される新しい機能です。されている現在の問題が管理されていると、実際に調査します。可能性があるときに解決 for Business Online の Office 365 と Skype の将来のビルドの機能が更新します。
  
## <a name="calling-plans-known-issues"></a>プランの既知の問題を呼び出す

|**既知の問題**|**コメント**|
|:-----|:-----|
|Tech Preview から移行する際に通話プランのライセンスを運用するライセンスしない自動的に更新ライセンス。  <br/> |新しいライセンスを購入まず、ユーザーに割り当てる準備ができるようにします。ユーザーのプロモーション (Tech Preview) のライセンスを削除して、**すぐに**新しい**国内通話プラン**または**国内と国際通話プラン**のライセンスをユーザーに割り当てます。<br/> 削除するが、複数のユーザーのライセンスを追加し、すべての Windows PowerShell を使用してユーザーからライセンスを削除して、し、**すぐに**すべての Windows PowerShell を使用しても、ユーザーのライセンスを割り当てることに非常に重要です。これがあることを確認しないサービスの中断大量のユーザーのライセンスの割り当てを処理する場合。サンプルの PowerShell スクリプト、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。<br/> **メモ:**ハイブリッドのユーザーを内部設置型 PSTN への接続を使用している場合は、する*のみ***電話システムで**ライセンスを割り当てる必要があります。**しないで**計画発信の音声を割り当てることもできます。ただしを有効にするには、Office 365 プランの呼び出しは Office 365 のユーザーに対して場合、は、まだ**国内通話プラン**またはそれらのユーザーの**国内と国際通話プラン**のライセンスを割り当てる必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。

> [!NOTE]
> これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。         |
   
## <a name="related-topics"></a>関連トピック
[電話番号のよく寄せられる質問を転送します。](transferring-phone-numbers-common-questions.md)

[さまざまなプランの呼び出し用の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理します。](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急の呼び出し元の条項および条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急発信免責事項のラベル](https://go.microsoft.com/fwlink/?LinkID=692099)
