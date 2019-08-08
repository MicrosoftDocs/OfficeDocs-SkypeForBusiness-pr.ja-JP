---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server は、単純な Url をサポートしています。
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239494"
---
# <a name="change-simple-urls-after-migration"></a>移行後の簡易 URL の変更

Skype for Business Server は、次の3つの簡単な Url をサポートしています。
  
- **会議**は、サイトまたは組織内のすべての会議のベース URL として使用されます。 [会議への参加] の [シンプル URL] を使用すると、会議に参加するためのリンクを簡単に理解して、簡単に連絡して配布することができます。 
    
- [**ダイヤル**イン] は、ダイヤルイン会議の設定の web ページにアクセスできるようにします。 ダイヤルインの簡易 URL は、会議にダイヤルインするユーザーが必要な電話番号と PIN 情報にアクセスできるように、すべての会議出席依頼に含まれています。 
    
- **管理者**が Skype For Business Server コントロールパネルにすばやくアクセスできるようにします。 管理者の簡易 URL は、組織の内部にあります。 
    
Skype for Business Server に移行した後、変更によって単純な Url の DNS レコードと証明書にどのような影響があるかを確認する必要があります。 従来の Skype for Business Server ディレクターがトポロジでまだ使用されている場合は、単純な Url への変更は必要ありません。 移行後に Skype for Business Server ディレクターがトポロジから削除された場合、Skype for Business サーバープールの1つをポイントするように、単純な URL の DNS レコードを更新する必要があります。 ただし、単純な URL 名を変更する場合は必ず、各ディレクターとフロントエンドサーバーで [ユーザーの有効化] を実行して、変更を登録する必要があります。

## <a name="to-update-the-meet-simple-url"></a>[シンプルの概要 URL を更新するには、

1. トポロジビルダーで、トップノードの**Skype For Business サーバー**を右クリックし、[**プロパティの編集**] をクリックします。
    
2. 左側のウィンドウで [**単純な url** ] を選び、[会議 url] を選び**ます。** [会議 url] を選び、[ **url の編集**] をクリックします。
    
3. URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。 
    
## <a name="to-update-the-admin-simple-url"></a>管理者の簡易 URL を更新するには

1. トポロジビルダーで、トップノードの**Skype For Business サーバー**を右クリックし、[**プロパティの編集**] をクリックします。
    
2. 左側のウィンドウで [**簡易 url** ] を選び、[**管理アクセス URL** ] ボックスに、Skype For business Server コントロールパネルへの管理アクセスに使用する単純な url を入力して、[ **OK]** をクリックします。
    
   > [!TIP]
   > 管理 URL には、できる限りシンプルな URL を使用することをお勧めします。 最も簡単なオプションhttps://adminはです。<em> \<ドメイン\></em>。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server の単純な Url の DNS 要件](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
