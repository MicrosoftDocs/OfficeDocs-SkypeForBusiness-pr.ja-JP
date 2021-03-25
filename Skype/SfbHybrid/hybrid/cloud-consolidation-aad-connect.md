---
title: AAD Connect を更新して複数のフォレストを含める
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、Teams と Skype for Business のクラウド統合の一環として複数のフォレストを含める AAD Connect を更新するための詳細な手順が含まれています。
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120376"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>AAD Connect を更新して複数のフォレストを含める

Azure AD Connect は、複数 [のフォレストからの同期をサポートしています](/azure/active-directory/connect/active-directory-aadconnect-topologies)。 ただし、Azure のインスタンスは 1 つのみサポートAD接続して AAD に同期します。 したがって、Azure ADが 1 つのフォレストに既にインストールされている場合は、AAD Connect の既存のインスタンスを更新して、追加のフォレストから同期する必要があります。

 - すべての ID が両方のフォレストで 1 回だけ表される場合 (つまり、メールが有効な連絡先を作成していない場合)、AAD Connect ウィザードを再び実行し、[同期オプションのカスタマイズ]を選択してから、[ディレクトリの接続] ページで追加のフォレストと creds の名前を入力します。<br><br>
 ![[ディレクトリの接続] ページ](../media/cloud-consolidation-connect-your-directories.png)
 - ただし、ユーザーが複数のディレクトリに存在し、データをマージする場合 (たとえば、別のフォレスト内のユーザーに対応するフォレストに連絡先オブジェクトが存在する場合)、Azure AD Connect をアンインストールして再インストールする必要があります。  これは、フォレスト間参加ルールの条件が最初のインストール時にのみ構成できるためです。 これは、次のページで行います。<br><br>
 ![[ユーザーを一意に識別する] ページ](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)