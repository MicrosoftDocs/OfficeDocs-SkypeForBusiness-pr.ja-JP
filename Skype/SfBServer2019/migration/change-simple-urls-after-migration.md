---
title: 移行後の簡易 URL の変更
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの Skype では、単純な Url をサポートします。
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892710"
---
# <a name="change-simple-urls-after-migration"></a>移行後の簡易 URL の変更

Skype ビジネス サーバーは、次の 3 つの簡単な Url をサポートしています。
  
- **対応**は、サイトまたは組織内のすべての会議のベース URL として使用されます。 対応の簡単な URL を使用して会議への参加へのリンクは、簡単に理解するには、簡単に通信して、配布です。 
    
- **ダイヤルインの**ダイヤルイン会議設定 web ページへのアクセスを有効にします。 会議にダイヤルインするユーザーが必要な電話番号と暗証番号 (pin) の情報にアクセスできるように、すべての会議出席依頼でダイヤルインの簡単な URL が含まれます。 
    
- **管理者**は、業務サーバーのコントロール パネルの Skype へのすばやいアクセスを使用できます。 管理の簡単な URL は、組織の内部に。 
    
に移行した後 Skype ビジネス サーバーの変更に及ぼす影響について、DNS レコードと証明書の簡単な Url に注意が必要です。 従来の Skype ビジネス サーバー ディレクターのトポロジの使用のままになります、簡単な Url への変更の必要はありません。 Skype ビジネス サーバー ディレクターの移行後のトポロジから削除する場合は、ビジネスのサーバー プールの Skype のいずれかを指すように簡単な URL の DNS レコードを更新しなければなりません。 簡単な URL 名を変更するたびに、変更を登録するには各ディレクターおよびフロント エンド サーバーで有効にする CsComputer を実行してください。

## <a name="to-update-the-meet-simple-url"></a>対応の簡単な URL を更新するには

1. トポロジ ビルダーでは、 **Skype**ビジネス サーバーは、最上位のノードを右クリックし、**プロパティの編集**] をクリックします。
    
2. 下、左側のウィンドウで**簡単な Url**を選択**会議 Url:** を満たす URL を選択し、 **[URL の編集**] をクリックします。
    
3. URL を目的の値に更新し、[**OK**] をクリックして編集した URL を保存します。 
    
## <a name="to-update-the-admin-simple-url"></a>管理の簡単な URL を更新するには

1. トポロジ ビルダーでは、 **Skype**ビジネス サーバーは、最上位のノードを右クリックし、**プロパティの編集**] をクリックします。
    
2. **管理アクセス URL** ] ボックスの下の左側のウィンドウで、**単純な Url**を選択、ビジネス サーバーのコントロール パネル、Skype への管理アクセスをする簡単な URL を入力し、[ **OK**] をクリックします。
    
   > [!TIP]
   > 管理 URL には、できる限りシンプルな URL を使用することをお勧めします。 最も簡単なオプションは、 https://admin。<em>\<ドメイン\></em>。 
  
## <a name="see-also"></a>関連項目

[Skype で簡単な Url のビジネス サーバー用の DNS の要件](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
