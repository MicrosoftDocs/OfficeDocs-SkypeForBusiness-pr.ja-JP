---
title: チーム ポリシー内の特殊文字の制限は?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: ポリシーおよびその修正を行うことができますの名前に特殊文字を含むが、どのような問題を参照してください。
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192165"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>チーム ポリシー内の特殊文字の制限は?

**チームで作成したポリシーの名前に特殊文字を使用できますが、しないことを強くお勧めします。**

ポリシー名の会議、チャット、および prescense を作成し、チームで他の作業などの特殊文字を持つことができます @、#、$。 ただし、ビジネス管理センターは、マイクロソフトのチームと Skype で名前を変更するしようとしている場合することはできませんにします。 Windows PowerShell と適切なポリシーのコマンドレットを使用して、変更する必要があります。

などの特殊文字を含む会議ポリシーがあり、名前を変更または名前から特殊文字を削除する場合は、セット CsMeetingPolicy コマンドレットを使用する必要があります。 

これを実行する必要がありますポリシー コマンドレットの一覧を以下に示します。
1. セット CsMeetingPolicy
2. セット CsAppPolicy
3. セット-*


