---
title: AAD は、複数のフォレストを含むように接続を更新します。
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、AAD のチームおよびビジネス用の Skype のためのクラウドの統合の一部として複数のフォレストを含むように接続を更新する詳細な手順が含まれています。
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247691"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>AAD は、複数のフォレストを含むように接続を更新します。

Azure AD 接続は、[複数のフォレストからの同期](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)をサポートします。 ただし、AAD と同期される Azure の AD 接続のインスタンスを 1 つだけをサポートします。 Azure AD が 1 つのフォレストに既にインストールされている場合、AAD の接続の既存のインスタンスを更新する必要がありますので、他のフォレストからの同期をします。

 - すべての id が 2 つのフォレスト全体で 1 回だけで表されている場合 (つまり、メールが有効な連絡先を行っていない、) 単に AAD の接続ウィザードを再実行、「同期オプションのカスタマイズ」を選択して**に、ディレクトリを接続し、** ページで、資格情報、その他のフォレストの名前を入力します。<br><br>
 ![接続]、[ディレクトリ] ページ](../media/cloud-consolidation-connect-your-directories.png)
 - ただしでユーザーが存在することができますより 1 つのディレクトリとすることをマージすることデータ (たとえば、連絡先オブジェクトは、別のフォレスト内のユーザーに対応するフォレスト内に存在) 場合、Azure AD 接続をアンインストールして再インストールをする必要があります。  最初のインストール中に、フォレスト間の結合規則の条件を構成するためです。 これは次のページで行います。<br><br>
 ![一意に識別する、ユーザーのページ](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>関連項目

[チームと Skype のビジネス向けのクラウド統合](cloud-consolidation.md)