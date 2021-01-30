---
title: Microsoft Teams での外部 (フェデレーション) ユーザーのネイティブ チャットエクスペリエンス
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
description: 両方のユーザーが TeamsOnly アップグレード モードにある Microsoft Teams の外部アクセス (フェデレーション) ユーザー向けネイティブ Teams チャット エクスペリエンスについて説明します。
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055659"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams での外部 (フェデレーション) ユーザーのネイティブ チャットエクスペリエンス

Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとチャットしている場合、チャットエクスペリエンスはテキストに制限されます。 ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、リッチフォーマット、@mentions、その他のチャット機能を含む "ネイティブ Teams チャット エクスペリエンス" を使用できます。 つまり、組織内のユーザーと同じように、他の組織の対象ユーザーと同じリッチな 1 対 1 の Teams チャット エクスペリエンスを利用できます。 他の組織のユーザーとのネイティブ Teams チャットは、1 対 1 のチャットに制限されます。

他の組織のユーザーのネイティブ チャットエクスペリエンスは、すべての Teams テナントに対して有効になりますが、すべてのユーザーが利用できるとは言えな。 ネイティブ チャットエクスペリエンスを提供するには、送信者と受信者の両方を TeamsOnly アップグレード モード用に構成する必要があります。 アップグレード ポリシーの詳細については、「共存とアップグレード [の設定」を参照してください](setting-your-coexistence-and-upgrade-settings.md)。

Teams で外部アクセス ユーザーの機能の一覧を表示するには、「外部アクセスとゲスト アクセスを比較する [」を参照してください](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>ネイティブ チャットに参加しているかどうかは、どのように知る必要がありますか?

チャット内のテキストを他の組織のユーザーとのみやり取りできる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。 書式設定、@mentions、絵文字など、他のすべてのチャット機能がある場合は、ネイティブの Teams チャットに参加しています。 

Teams は、他の組織のユーザーのアップグレード モードを定期的にチェックし、TeamsOnly アップグレード モードで Teams を実行しているユーザーを見つけたら、ネイティブの Teams チャットに切り替えて元のチャットをロックするように求めるメッセージが表示されます。

ネイティブの Teams チャットに切り替えても、Teams は 2 つの会話を結合しません。 代わりに、両方のチャットがチャット フィードに表示されます。 新しいネイティブ Teams チャットはアクティブですが、古いテキスト専用のチャットはロックされています。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>ユーザーが Teams のみモードではなくなった場合は、どうなるでしょうか。

他の組織のユーザーとネイティブの Teams チャットを行っている場合、そのうちの 1 人が TeamsOnly アップグレード モードから切り替わると、Teams はネイティブの Teams チャットをロックし、制限付きテキスト専用チャットのリンクを提供します。 ネイティブの Teams チャットを続行できない。 ネイティブの Teams チャットは引き続き読み取り可能ですが、そこで会話を続けはまだできます。

Teams が、このユーザーとの古いテキスト専用チャットを見つけた場合、そのチャットは復活します。 それ以外の場合、Teams は新しいテキスト専用チャットを作成します。


## <a name="related-topics"></a>関連項目

[Teams で外部アクセスを管理する](manage-external-access.md)
