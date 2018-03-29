---
title: Skype for Business Server 2015 での発信者番号のプレゼンテーションの変換ルールの作成または変更
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '概要: ビジネス サーバーのコントロール パネルの Skype を使用して、呼び出し元の ID を構成する方法を説明します。'
ms.openlocfilehash: b5460558d621b04ca041bd540f9aba9d3a19bd45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での発信者番号のプレゼンテーションの変換ルールの作成または変更
 
**の概要:**ビジネス サーバーのコントロール パネルの Skype を使用して、呼び出し元の ID を構成する方法について説明します。
  
ビジネス サーバー、呼び出し先の電話番号を Skype で (つまり、電話番号と呼ばれる) (つまり、関連付けられているゲートウェイ、構内交換 (_トランク ピア_で必要とされるローカルのダイヤル形式に E.164 形式から変換することができますPBX)、または SIP トランク)。 これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。
  
Skype ビジネス サーバーのもこともできますも呼び出し元の関係者の電話番号 (つまりからの呼び出し元の呼び出しは、電話番号) を翻訳する E.164 形式からトランク ピアで必要とされるローカルのダイヤル形式にします。 たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、呼び出し元の ID を構成するのには

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. 左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。
    
3. [**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。
    
4. 発信者番号のプレゼンテーションを構成するには、次のようにします。
    
   - エンタープライズ VoIP 展開で利用可能なすべての変換ルールの一覧から 1 つまたは複数のルールを選択するのには [**選択**] をクリックします。 [**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。
    
   - 新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。 新しいルールを定義する方法については、展開に関するドキュメントの[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。
    
   - 既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。 詳細については、展開に関するドキュメントの[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。
    
   - 既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。 詳細については、[変換ルールの定義](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)を参照してください。 
    
   - トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。
    
    > [!CAUTION]
    > 関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。 
  

