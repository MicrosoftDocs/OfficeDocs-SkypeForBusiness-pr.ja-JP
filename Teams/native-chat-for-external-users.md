---
title: 外部 (フェデレーション) ユーザーのネイティブ チャット エクスペリエンスMicrosoft Teams
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
description: 両方のユーザーが TeamsOnly アップグレード モードTeamsの外部アクセス (フェデレーション) ユーザーのネイティブ Microsoft Teams チャット エクスペリエンスについて学習します。
ms.openlocfilehash: 02bf09a7623079eb207ffca1b122bc03bf07c5c8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240463"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>外部 (フェデレーション) ユーザーのネイティブ チャット エクスペリエンスMicrosoft Teams

ユーザーがMicrosoft Teams (フェデレーション) ユーザーとチャットしている場合、チャット エクスペリエンスはテキストに制限されます。 ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、リッチフォーマット、@mentions、その他のチャット機能を含む "ネイティブ Teams チャット エクスペリエンス" を使用できます。 ネイティブ Teams他の組織のユーザーとのチャットは、1 対 1 のチャットにのみ制限されます。

他の組織のユーザーのネイティブ チャット エクスペリエンスは、すべてのテナントTeamsオンになりますが、すべてのユーザーが資格を持っているというのではありません。 ネイティブ チャット エクスペリエンスを提供するには、送信者と受信者の両方を TeamsOnly アップグレード モード用に構成する必要があります。 アップグレード ポリシーの詳細については、「共存とアップグレードの設定 [」を参照してください](setting-your-coexistence-and-upgrade-settings.md)。

外部アクセス ユーザーの機能の一覧を表示するには、Teamsとゲスト アクセスの比較に関する[ページを参照してください](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>ネイティブ チャットに参加しているかどうかは、どうすれば知るのですか?

チャット内のテキストを他の組織のユーザーとのみ交換できる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。 書式設定、@mentions、絵文字など、その他のチャット機能がある場合は、ネイティブチャットTeamsしています。 

Teamsは、他の組織のユーザーのアップグレード モードを定期的にチェックし、TeamsOnly アップグレード モードで Teams を実行しているユーザーを見つけたら、ネイティブ Teams チャットに切り替えて元のチャットをロックするように求めるメッセージが表示されます。

ネイティブ チャットに切り替Teams、Teams 2 つの会話は結合しません。 代わりに、両方のチャットがチャット フィードに表示されます。 新しいネイティブ チャットTeamsアクティブですが、古いテキスト専用チャットはロックされています。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>ユーザーが [のみ] モードTeams場合は、どうなるでしょうか。

他の組織のユーザーとネイティブ Teams チャットを行っている場合、そのうちの 1 人が TeamsOnly アップグレード モードから切り替わると、Teams はネイティブ Teams チャットをロックし、制限付きテキスト専用チャットのリンクを提供します。 ネイティブ チャットを続行Teamsされます。 ネイティブ のチャットを読Teams、そこで会話を続けはまだできない場合があります。

このTeams古いテキスト専用チャットを見つけた場合、そのチャットは復活します。 それ以外のTeams、新しいテキスト専用チャットが作成されます。


## <a name="related-topics"></a>関連トピック

[Teams で外部アクセスを管理する](manage-external-access.md)
