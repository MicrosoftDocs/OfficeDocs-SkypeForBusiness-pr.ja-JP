---
title: Microsoft Teams の外部 (フェデレーション) ユーザー向けネイティブ チャット エクスペリエンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 両方のユーザーが TeamsOnly アップグレード モードにある Microsoft Teams の外部アクセス (フェデレーション) ユーザーのネイティブ Teams チャット エクスペリエンスについて説明します。
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030117"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams の外部 (フェデレーション) ユーザー向けネイティブ チャット エクスペリエンス

Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとチャットしている場合、チャット エクスペリエンスはテキストに制限されます。 ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、リッチ フォーマット、@mentions、その他のチャット機能を含む"ネイティブ Teams チャット エクスペリエンス" を使用できます。 他の組織のユーザーとのネイティブ Teams チャットは、1 対 1 のチャットにのみ制限されます。

他の組織のユーザーのネイティブ チャット エクスペリエンスは、すべての Teams テナントで有効になりますが、すべてのユーザーが対象となるとは言えなかっています。 ネイティブ チャット エクスペリエンスを提供するには、送信者と受信者の両方を TeamsOnly アップグレード モード用に構成する必要があります。 アップグレード ポリシーの詳細については、「共存とアップグレードの [設定の設定」を参照してください](setting-your-coexistence-and-upgrade-settings.md)。

Teams の外部アクセス ユーザーの機能の一覧を表示するには、「外部アクセスとゲスト アクセスを比較する」 [を参照してください](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>ネイティブ チャットに参加しているかどうかは、どうすれば分かるのか?

チャット内のテキストのみを他の組織のユーザーと交換できる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。 書式設定、@mentions、絵文字など、他のすべてのチャット機能がある場合は、ネイティブ Teams チャットに参加しています。 

Teams は、他の組織のユーザーのアップグレード モードを定期的にチェックし、TeamsOnly アップグレード モードで Teams を実行しているチームを見つけたら、ネイティブの Teams チャットに切り替えて元のチャットをロックするように求めるメッセージが表示されます。

ネイティブの Teams チャットに切り替えても、Teams は 2 つの会話をマージしません。 代わりに、チャット フィードに両方のチャットが表示されます。 新しいネイティブ Teams チャットはアクティブですが、古いテキスト専用チャットはロックされています。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>ユーザーが Teams Only モードでなくなった場合は、どうなるでしょうか。

他の組織のユーザーとネイティブ Teams チャットを行っている場合、そのうちの 1 人が TeamsOnly アップグレード モードから切り替わると、Teams はネイティブ Teams チャットをロックし、テキスト専用の制限付きチャットのリンクを提供します。 ネイティブ Teams チャットを続行できない。 ネイティブの Teams チャットは引き続き読み取り可能ですが、そこで会話を続行できない場合があります。

Teams が、このユーザーと古いテキスト専用チャットを見つけた場合、そのチャットが再び表示されます。 それ以外の場合、Teams は新しいテキスト専用チャットを作成します。


## <a name="related-topics"></a>関連項目

[Teams で外部アクセスを管理する](manage-external-access.md)
