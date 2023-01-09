---
title: Microsoft Teams の外部 (フェデレーション) ユーザー向けのネイティブ チャット エクスペリエンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 両方のユーザーが TeamsOnly アップグレード モードになっている Microsoft Teams の外部アクセス (フェデレーション) ユーザーのネイティブ Teams チャット エクスペリエンスについて説明します。
ms.openlocfilehash: 759ad4f03de099637df0e92a7a8925a7c18ae3fd
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740802"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams の外部 (フェデレーション) ユーザー向けのネイティブ チャット エクスペリエンス

Microsoft Teams ユーザーが外部 (フェデレーション) ユーザーとチャットしている場合、チャット エクスペリエンスはテキストに制限されます。 ただし、Teams ユーザーと別の組織のユーザーの両方が TeamsOnly アップグレード モードの場合は、豊富な書式設定、@メンション、その他のチャット機能を含む "ネイティブ Teams チャット エクスペリエンス" を使用できます。

他の組織のユーザーのネイティブ チャット エクスペリエンスは、すべての Teams テナントで有効になっていますが、すべてのユーザーが資格を持つわけではありません。 ネイティブ チャット エクスペリエンスが提供されるには、送信者と受信者の両方が TeamsOnly アップグレード モード用に構成されている必要があります。 アップグレード ポリシーの詳細については、「[共存とアップグレードの設定の設定](setting-your-coexistence-and-upgrade-settings.md)」を参照してください。

Teams の外部アクセス ユーザーの機能の一覧については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。

> [!NOTE]
> ネイティブ チャット エクスペリエンスは、Microsoft 365 クラウド環境間では使用できません。Microsoft 365 WorldWide (GCC を含む) から GCC High、GCC High from/to DoD、または WW from/to DoD。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>ネイティブ チャットに参加しているかどうかを知る方法。

他の組織のユーザーとチャットでテキストをのみ交換できる場合は、標準の外部アクセス (フェデレーション) チャットに参加しています。 書式設定、@メンション、絵文字など、他のチャット機能がある場合は、ネイティブ Teams チャットに参加しています。 

Teams では、他の組織のユーザーのアップグレード モードが定期的にチェックされ、TeamsOnly アップグレード モードで Teams を実行しているユーザーが見つかると、ネイティブ Teams チャットに切り替えて元のチャットをロックするように求められます。

ネイティブ Teams チャットに切り替えると、Teams により 2 つの会話は結合されません。 代わりに、両方のチャットがチャット フィードに表示されます。 新しいネイティブ Teams チャットはアクティブですが、古いテキストのみのチャットはロックされています。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>ユーザーが TeamsOnly モードでなくなった場合はどうなりますか?

他の組織のユーザーとネイティブ Teams チャットを行っていた場合、そのユーザーの 1 人が TeamsOnly アップグレード モードから切り替えられた場合、Teams はネイティブ Teams チャットをロックし、制限付きのテキストのみのチャットのリンクを提供します。 ネイティブ Teams チャットを続行することはできません。 ネイティブ Teams チャットは引き続き読むことができますが、そこで会話を続けることはできません。

Teams でこのユーザーとの古いテキストのみのチャットが見つかると、そのチャットが再生されます。 それ以外の場合、Teams は新しいテキストのみのチャットを作成します。


## <a name="related-topics"></a>関連項目

[Teams で外部アクセスを管理する](manage-external-access.md)
