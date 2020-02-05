---
title: Skype for Business Server で発信者 ID のプレゼンテーションの翻訳ルールを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '概要: Skype for Business Server コントロールパネルを使用して発信者番号認識を構成する方法について説明します。'
ms.openlocfilehash: d6b2e594d0f16e9b3278145087af854650a957da
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768160"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Skype for Business Server で発信者 ID のプレゼンテーションの翻訳ルールを作成または変更する

**概要:** Skype for Business Server コントロールパネルを使用して発信者番号認識を構成する方法について説明します。

Skype for Business Server では、発信元の国の電話番号 (電話番号) を、_トランクのピア_によって要求されるローカルのダイヤル形式 (関連付けられているゲートウェイ、構内交換機 (PBX)、SIP トランクなど) に変換することができます。 これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。

Skype for Business Server では、発信者の電話番号 (つまり、発信者が発信した電話番号) を、樹幹形式から、トランクピアが必要とする地域のダイヤル形式に翻訳するオプションも提供されます。 たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して発信者番号認識を構成するには

1. Skype for Business Server コントロールパネルを開きます。

2. 左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。

3. [**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。

4. 発信者番号のプレゼンテーションを構成するには、次のようにします。

   - エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。 [**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。

   - 新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。 新しいルールの定義の詳細については、「展開ドキュメントで[翻訳ルールを定義](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)する」を参照してください。

   - 既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。詳細については、「展開」のドキュメントの「  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。

   - 既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。詳細については、「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。

   - トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。

     > [!CAUTION]
     > 関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。


