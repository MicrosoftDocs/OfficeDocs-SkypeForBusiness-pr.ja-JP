---
title: Create or modify a translation rule for caller ID presentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server コントロール パネルを使用して発信者番号を構成する方法について学習します。'
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804187"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Create or modify a translation rule for caller ID presentation in Skype for Business Server

**概要:** Skype for Business Server コントロール パネルを使用して発信者番号を構成する方法について学習します。

Skype for Business Server では、呼び出し側の電話番号 (つまり、呼び出された電話番号) を E.164 形式から、トランク ピア  _(つまり_ 、関連付けられたゲートウェイ、PBX (PBX)、または SIP トランク) で必要なローカルダイヤル形式に変換できます。 これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。

また、Skype for Business Server では、発信者の電話番号 (発信者が発信元の電話番号) を E.164 形式からトランク ピアで必要なローカル ダイヤル形式に変換することもできます。 たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して発信者番号を構成するには

1. Skype for Business Server コントロール パネルを開きます。

2. 左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**トランク構成**] をクリックします。

3. [**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。

4. 発信者番号のプレゼンテーションを構成するには、次のようにします。

   - エンタープライズ VoIP 展開で利用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、**[選択]** をクリックします。 [**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。

   - 新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。 新しいルールの定義の詳細については、「展開」のドキュメントの  [「Defining Translation Rules」](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) を参照してください。

   - 既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。 詳細については、「展開」のドキュメントの「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。

   - 既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。 詳細については、「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。

   - トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。

     > [!CAUTION]
     > 関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。


