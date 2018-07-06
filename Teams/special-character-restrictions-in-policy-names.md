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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205079"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>チーム ポリシー内の特殊文字の制限は?

**PowerShell でチームのポリシーを作成するための特殊文字を使用できますが、これらのポリシーを管理する制限されます。 このため、ポリシーの名前に特殊文字が含まれていないを強くお勧めします。**

PowerShell を使用して会議を作成し、チームでチャットするポリシー名は次のように特殊文字を持つことができます @、#、$。 ただし、ビジネス管理センターは、マイクロソフトのチームと Skype でポリシーを編集しようとしている場合することはできませんにします。 Windows PowerShell と適切なポリシーのコマンドレットを使用して、変更する必要があります。

使用する必要があります特別な文字を使用して、ポリシーのオブジェクトがあり、ビジネス管理センターは、マイクロソフトのチームと Skype でポリシーを効率的に管理するために特殊文字を削除する場合、手順の下。 

注: 明確手順メッセージング ポリシーの例をここで使用します。  同じプロセス subsituting 関連のコマンドレットで別のポリシーの種類 (たとえば会議) に使用されます。 

1) Get CSMessagingPolicy を呼び出す-< old_policy_name > を識別し、ポリシーの出力をキャプチャします。
2) 呼び出しのセット CSMessagingPolicy-< new_policy_name > を識別名に特殊文字を含まない元のポリシーとしては、同じ構成で新しいポリシーを作成します。
3) 削除 CSMessagingPolicy を呼び出す-ポリシーを削除する < old_policy_name > を識別します。  このコマンドが成功すると、完了し、ビジネス管理センターの PowerShell またはマイクロソフトのチームと Skype のいずれかを使用して新しいポリシーをユーザーの割り当てを開始します。
4) 上記のコマンドが成功しない場合は、古いポリシーは、ユーザーに割り当てられているので、です。  ユーザーからポリシーの割り当てを解除、新規のポリシーを適用し、dwlete をもう一度実行するコマンドレット実行の割り当てを解除します。


