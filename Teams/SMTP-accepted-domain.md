---
title: "Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加し、チーム メンバーに通知を送信する方法を説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 2006cde3cf2fc41a64b98fdc14004aa64876cb1a
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する 
=============================================================================

管理コンソールに Office 365 グループを作成するか、Outlook を使って Office 365 グループを作成するかに関わらず、グループに追加したチーム メンバーへの通知の送信には Exchange Online が使用されます。通知は、既定のドメイン SMTP FQDN であるテナントから生成されます。

![Outlook 電子メールの、ユーザーがグループに追加されたことを示すメッセージ ヘッダーの例を示すスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams は追加済みのチーム メンバーに通知を送信するために Microsoft Exchange Online も使用します。SMTP メッセージのドメイン FQDN の場合は、「@email.teams.microsoft.com」という形式が使用され、この形式はスパム フィルタリングによって検出されます。次の画像が示すように、Outlook はこのメッセージを外部送信者として認識し、画像や特定のコンテンツの遮断といった標準的なセキュリティ機能を適用します。

![Outlook 電子メールの、ユーザーがグループに追加されたことを示すメッセージ ヘッダーの例を示すスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最良の結果と円滑な操作を実現するため、Microsoft Teams SMTP ドメインを Exchange Online スパム構成の「承認済みドメイン」リストに追加することをお勧めします。

![Exchange Online スパム構成の [許可] リスト セクションのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
