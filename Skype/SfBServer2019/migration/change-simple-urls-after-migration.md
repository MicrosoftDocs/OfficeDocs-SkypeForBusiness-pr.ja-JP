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
description: Skype for Business Server は簡易 Url をサポートしています。
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753907"
---
# <a name="change-simple-urls-after-migration"></a>移行後の簡易 URL の変更

Skype for Business Server は、次の3つの簡単な Url をサポートします。
  
- **Meet**は、サイトまたは組織内のすべての電話会議のベース URL として使用されます。 簡単な会議 URL を使用すると、会議に参加するためのリンクが覚えやすくなり、通知も配布も簡単になります。 
    
- **ダイヤル**インは、ダイヤルイン会議設定 web ページへのアクセスを有効にします。 ダイヤルインの簡易 URL は、すべての会議出席依頼に含まれているため、会議にダイヤルインするユーザーは必要な電話番号と PIN 情報にアクセスできます。 
    
- **管理者**は、Skype For Business Server コントロールパネルにすばやくアクセスできます。 簡単な管理 URL は、組織内部の URL です。 
    
Skype for Business Server に移行した後は、簡単な Url の DNS レコードと証明書に対する変更による影響に注意する必要があります。 従来の Skype for Business Server のディレクターがトポロジで使用されている場合は、簡易 Url を変更する必要はありません。 移行後に、Skype for Business Server ディレクターがトポロジから削除された場合は、簡易 URL の DNS レコードを更新して、Skype for Business サーバープールの1つをポイントする必要があります。 ただし、簡易 URL 名を変更する場合は必ず、各ディレクターおよびフロントエンド サーバーで Enable-CsComputer を実行して変更を登録する必要があります。

## <a name="to-update-the-meet-simple-url"></a>簡単な会議 URL を更新するには

1. [トポロジビルダー] で、最上位ノードの [ **Skype For Business Server**] を右クリックし、[**プロパティの編集**] をクリックします。
    
2. 左側のウィンドウで [**簡易 url** ] を選択し、[**会議の url:** ] の下の [url の**編集**] をクリックします。
    
3. URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。 
    
## <a name="to-update-the-admin-simple-url"></a>管理者の簡易 URL を更新するには

1. [トポロジビルダー] で、最上位ノードの [ **Skype For Business Server**] を右クリックし、[**プロパティの編集**] をクリックします。
    
2. [**簡易 url**の選択] 左側のウィンドウで、[**管理アクセス url** ] ボックスに、Skype For business Server コントロールパネルへの管理アクセスに使用する簡易 url を入力し、[ **OK**] をクリックします。
    
   > [!TIP]
   > 管理 URL にできるだけ簡易 URL を使用することをお勧めします。 最も簡単なオプションは、 https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server の簡易 Url の DNS 要件](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
