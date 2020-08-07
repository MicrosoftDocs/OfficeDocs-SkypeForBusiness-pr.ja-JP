---
title: Microsoft Teams の外部 (フェデレーション) ユーザー向けのネイティブチャット操作
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams の外部アクセス (フェデレーション) ユーザー向けのネイティブなチームチャットエクスペリエンスについて説明します。この機能は、両方のユーザーが teams Sonly アップグレードモードを使用している外部ユーザー間で利用できます。
ms.openlocfilehash: 1274e71f5854e05049c8d766bd3456a0792b1032
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583846"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams の外部 (フェデレーション) ユーザー向けのネイティブチャット操作
======================================

Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとのチャットを行っている場合、チャットエクスペリエンスはテキストに制限されます。 ただし、Teams ユーザーと外部ユーザーの両方が TeamsOnly アップグレードモードに入っている場合は、"ネイティブチームチャットエクスペリエンス" を使用できます。これには、リッチな書式設定、@mentions、その他のチャット機能が含まれます。 つまり、組織内のユーザーと同じように、適切な外部ユーザーと同じ1:1 チームチャットエクスペリエンスを提供することができます。 外部ユーザーとのネイティブチームチャットは、依然として1:1 のチャットに限定されます (外部ユーザーはグループチャットを行うことはできません)。

外部ユーザー向けのネイティブチャット操作は、すべてのチームテナントで有効になっていますが、すべてのユーザーが対象になっているわけではありません。 ネイティブチャットエクスペリエンスを提供するには、送信者と受信者の両方が teams s アップグレードモード用に構成されている必要があります。 アップグレードポリシーの詳細については、「[共存の設定とアップグレードの設定](setting-your-coexistence-and-upgrade-settings.md)」を参照してください。

Teams の外部アクセスユーザーの機能の一覧については、「[外部とゲストのアクセスを比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)する」を参照してください。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>自分がネイティブチャットであるかどうかを知る方法を教えてください。

チャット内のテキストを外部ユーザーとのみ交換できる場合は、標準の外部アクセス (フェデレーション) チャットを使用しています。 書式設定、@mentions、絵文字など、その他のすべてのチャット機能を使用している場合は、ネイティブのチームとの間で、外部ユーザーとチャットしていることになります。 

チームは定期的に外部ユーザーのアップグレードモードを確認します。チームは、Teams のアップグレードモードで Teams を実行している外部ユーザーを見つけたときに、ネイティブのチームチャットに切り替えて、元のチャットをロックするように求められます。

ネイティブなチームチャットに切り替えると、Teams では2つの会話が結合されません。 代わりに、チャットフィードに両方のチャットが表示されます。 新しいネイティブチームチャットはアクティブですが、以前のテキストのみのチャットはロックされています。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>ユーザーが Teams のみモードになっていない場合はどうなりますか?

ネイティブなチームで外部ユーザーとチャットしていて、どちらか一方が teams のアップグレードモードに切り替えられている場合、チームはネイティブのチームチャットをロックし、テキストのみのチャットを制限したリンクを提供します。 ネイティブの Teams チャットを続行することはできません。 ただし、ネイティブの Teams チャットを読むことはできますが、そこで会話を続けることはできません。

Teams では、この外部ユーザとのテキストのみのチャットが見つかると、そのチャットが使おうます。 それ以外の場合、チームは新しいテキストのみのチャットを作成します。


## <a name="related-topics"></a>関連トピック

[Teams で外部アクセスを管理する](manage-external-access.md)
