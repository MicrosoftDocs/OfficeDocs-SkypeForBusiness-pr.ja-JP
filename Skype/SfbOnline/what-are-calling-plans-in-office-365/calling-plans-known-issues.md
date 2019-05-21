---
title: 通話プランの既知の問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Office 365 の通話プラン (PSTN 通話) に関する既知の問題とその対処方法について説明します。 '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299526"
---
# <a name="calling-plans-known-issues"></a>通話プランの既知の問題

Office 365 の通話プランは、Skype for Business Online の新機能です。 次のような現在の問題が追跡され、積極的に調査されています。 今後のビルドの Office 365 および Skype for Business Online で機能が更新されると、これらの機能が解決される可能性があります。
  
## <a name="calling-plans-known-issues"></a>通話プランの既知の問題

|**既知の問題**|**コメント**|
|:-----|:-----|
|技術プレビューのライセンスを、通話プランの運用ライセンスに移行しても、ライセンスが自動的に更新されることはありません。  <br/> |最初に新しいライセンスを購入して、ユーザーに割り当てる準備ができたことを確認します。 ユーザーからプロモーション (Tech Preview) ライセンスを削除し、新しい**国内通話プラン**または**国内および国際通話プラン**のライセンスをユーザーに**直ち**に割り当てます。 <br/> 複数のユーザーのライセンスを削除して追加する場合は、Windows PowerShell を使用しているすべてのユーザーからライセンスを削除し、Windows PowerShell を使用してすべてのユーザーのライセンスを**直ち**に割り当てることが非常に重要です。 こうすることで、大量のユーザーライセンスの割り当てを処理する際にサービスが中断されることがなくなります。 PowerShell スクリプトの例については、「 [Skype For business および Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」を参照してください。  <br/> **注:** ハイブリッドユーザー用にオンプレミスの PSTN 接続を使用して** いる場合は、**電話システム**のライセンスを割り当てる必要があります。 音声通話プランを割り当てることはでき**ません**。 ただし、office 365 の通話プランを有効にしている場合、Office 365 のユーザーには、**国内通話プラン**または**国内および国際通話プラン**のライセンスを割り当てる必要があります。 [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。

> [!NOTE]
> その他の電話番号を取得する必要がある場合は、[ビジネス製品のサポートにお問い合わせください。管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 