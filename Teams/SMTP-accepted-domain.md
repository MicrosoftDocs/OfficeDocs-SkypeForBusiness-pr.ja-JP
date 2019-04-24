---
title: Microsoft Teams SMTP ドメインを承認済みの送信者ドメインとして Exchange Online に追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: マイクロソフト チーム SMTP ドメインを追加、許可された送信者のドメインと Exchange オンラインのチーム メンバーに通知を送信するについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4a1a94bec69b1c7953dea6802d62058b04700bb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194172"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Microsoft Teams SMTP ドメインを承認済みの送信者ドメインとして Exchange Online に追加する 
=============================================================================

管理コンソールに Office 365 グループを作成するか、Outlook を使って Office 365 グループを作成するかに関わらず、グループに追加したチーム メンバーへの通知の送信には Exchange Online が使用されます。通知は、既定のドメイン SMTP FQDN であるテナントから生成されます。

![Outlook 電子メールの、ユーザーがグループに追加されたことを示すメッセージ ヘッダーの例を示すスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

チームを使用して Microsoft Exchange Online にも追加されたことをチーム メンバーに通知します。 ドメインの SMTP メッセージの FQDN に違いテナントの商業とビジネスの"@email.teams.microsoft.com"と政府のテナントの「@GCC-email.teams.com」は、迷惑メール フィルターによってキャッチされる可能性があります。

![Outlook 電子メールの、ユーザーがグループに追加されたことを示すメッセージ ヘッダーの例を示すスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最良の結果とシームレスな操作では、Exchange オンラインの迷惑メール構成の「許可された送信者のドメイン] 一覧に、マイクロソフト チームの SMTP ドメインを追加することを検討します。

![Exchange Online スパム構成の [許可] リスト セクションのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
