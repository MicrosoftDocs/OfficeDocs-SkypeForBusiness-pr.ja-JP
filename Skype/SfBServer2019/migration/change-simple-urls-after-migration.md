---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server URL をサポートしています。
ms.openlocfilehash: c3d78387ae0bcf16204e2fcaa4ff7db3549334fe814a014a88c80e8ab6658d5b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324726"
---
# <a name="change-simple-urls-after-migration"></a>移行後の簡易 URL の変更

Skype for Business Serverは、次の 3 つの単純な URL をサポートしています。
  
- **Meet** は、サイトまたは組織のすべての会議の基本 URL として使用されます。 簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。 
    
- **ダイヤルインを使用すると**、Web ページからダイヤルイン会議設定できます。 ダイヤルイン簡易 URL は、すべての会議出席依頼に含まれているので、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。 
    
- **管理者** は、コントロール パネルへのクイック Skype for Business Serverを有効にします。 簡単な管理 URL は、組織内部の URL です。 
    
移行後、Skype for Business Server URL の DNS レコードと証明書に対する変更の影響を認識する必要があります。 レガシ Skype for Business Serverディレクターがトポロジで使用されている場合は、単純な URL を変更する必要はありません。 移行後Skype for Business Serverディレクターがトポロジから削除された場合は、単純な URL DNS レコードを更新して、新しいプールの 1 Skype for Business Serverする必要があります。 ただし、簡易 URL 名を変更する場合は必ず、各ディレクターおよびフロントエンド サーバーで Enable-CsComputer を実行して変更を登録する必要があります。

## <a name="to-update-the-meet-simple-url"></a>Meet 簡易 URL を更新するには

1. トポロジ ビルダーで、上部のノードを右クリックし、[プロパティ **Skype for Business Server]****をクリックします**。
    
2. 左側 **のウィンドウで [単純な URL]** を選択し、[会議 URL] の下にある [会議 **URL]** を選択し、[URL の編集] **をクリックします**。
    
3. URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。 
    
## <a name="to-update-the-admin-simple-url"></a>管理者の簡易 URL を更新するには

1. トポロジ ビルダーで、上部のノードを右クリックし、[プロパティ **Skype for Business Server]****をクリックします**。
    
2. 左側 **のウィンドウで [単純な** URL] を選択し、[管理アクセス **URL]** ボックスの下に、Skype for Business Server コントロール パネルへの管理アクセスに使用する単純な URL を入力し **、[OK]** をクリックします。
    
   > [!TIP]
   > 管理 URL にできるだけ簡易 URL を使用することをお勧めします。 最も簡単なオプションは https://admin . <em>\<domain\></em> 
  
## <a name="see-also"></a>関連項目

[ドメイン内の単純な URL の DNS 要件Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
