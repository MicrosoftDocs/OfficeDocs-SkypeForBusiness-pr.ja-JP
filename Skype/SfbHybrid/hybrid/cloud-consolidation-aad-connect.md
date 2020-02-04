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
description: この付録には、Teams 接続を更新して、Teams と Skype for Business のクラウド統合の一部として複数のフォレストを含めるための詳細な手順が含まれています。
ms.openlocfilehash: 3d3d72c14957f0ed8932d95fcd2dbe9ec9c1e37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696062"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>AAD Connect を更新して複数のフォレストを含める

Azure AD Connect は、[複数のフォレストからの同期を](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)サポートしています。 ただし、AAD に対して Azure AD Connect 同期のインスタンスを1つだけサポートしています。 そのため、Azure AD が1つのフォレストに既にインストールされている場合は、AAD Connect の既存のインスタンスを追加のフォレストから同期するように更新する必要があります。

 - 両方のフォレストですべての id が1回のみ表示されている場合 (つまり、メールが有効な連絡先がない場合)、AAD Connect ウィザードを再実行し、[同期オプションのカスタマイズ] を選択してから、[**ディレクトリの接続**] ページで追加のフォレストおよび資格情報の名前を入力するだけです。<br><br>
 ![[ディレクトリの接続] ページ](../media/cloud-consolidation-connect-your-directories.png)
 - ただし、ユーザーが複数のディレクトリに存在し、データを結合する場合 (たとえば、別のフォレストのユーザーに対応する連絡先オブジェクトがフォレスト内に存在する場合)、Azure AD Connect をアンインストールしてから再インストールする必要があります。  これは、フォレスト間の参加ルールの条件は、最初のインストール時にのみ構成できるからです。 これは、次のページで行われます。<br><br>
 ![ユーザーを一意に識別するページ](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>関連項目

[Teams と Skype for Business のクラウド統合](cloud-consolidation.md)