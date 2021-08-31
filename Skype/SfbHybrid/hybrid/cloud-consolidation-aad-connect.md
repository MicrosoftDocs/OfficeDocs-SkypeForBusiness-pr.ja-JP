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
ms.localizationpriority: medium
description: この付録には、AAD Connectを更新して、クラウド統合の一部として複数のフォレストを含めるTeamsおよびSkype for Business。
ms.openlocfilehash: 261085c85b9b3114bce49216e7b63173cd37d55e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731886"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>AAD Connect を更新して複数のフォレストを含める

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD Connectは、複数[のフォレストからの同期をサポートしています](/azure/active-directory/connect/active-directory-aadconnect-topologies)。 ただし、AAD と同期する Azure AD Connectインスタンスは 1 つしかサポートされません。 したがって、Azure AD が 1 つのフォレストに既にインストールされている場合は、AAD Connect の既存のインスタンスを更新して、追加のフォレストから同期する必要があります。

 - すべての ID が両方のフォレストで 1 回だけ表される場合 (つまり、メールが有効な連絡先を作成していない場合)、AAD Connect ウィザードを再び実行し、[同期オプションのカスタマイズ] を選択してから **、[Connect Your Directories]** ページで追加のフォレストと creds の名前を入力します。<br><br>
 ![[ディレクトリConnect] ページが表示されます。](../media/cloud-consolidation-connect-your-directories.png)
 - ただし、ユーザーが複数のディレクトリに存在し、データをマージする場合 (たとえば、別のフォレスト内のユーザーに対応するフォレストに連絡先オブジェクトが存在する場合)、Azure AD Connect をアンインストールして再インストールする必要があります。  これは、フォレスト間参加ルールの条件が最初のインストール時にのみ構成できるためです。 これは、次のページで行います。<br><br>
 ![[ユーザーを一意に識別する] ページ。](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>関連項目

[クラウドの統合 :TeamsとSkype for Business](cloud-consolidation.md)