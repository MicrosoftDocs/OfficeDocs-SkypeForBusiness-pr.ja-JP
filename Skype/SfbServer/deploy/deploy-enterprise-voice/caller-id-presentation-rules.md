---
title: 発信者番号プレゼンテーションの翻訳ルールを作成または変更Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '概要: [コントロール パネル] を使用して発信者 ID を構成するSkype for Business Serverします。'
ms.openlocfilehash: 13ca5073956e6cf67264e706a82e63ec72efbac4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865334"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>発信者番号プレゼンテーションの翻訳ルールを作成または変更Skype for Business Server

**概要:**[コントロール パネル] コントロール パネルを使用して発信者 ID をSkype for Business Serverします。

Skype for Business Server では、通話相手の電話番号 (つまり、呼び出された電話番号) を E.164 形式から、トランク ピア _(つまり_、関連付けられたゲートウェイ、プライベート ブランチ 交換 (PBX)、または SIP トランク) で必要なローカル ダイヤル形式に変換できます。 これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。

Skype for Business Serverには、発信者の電話番号 (発信者が呼び出している電話番号) を E.164 形式からトランク ピアで必要なローカル ダイヤル形式に変換することもできます。 たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して発信者 ID をSkype for Business Serverするには

1. [コントロール Skype for Business Server] を開きます。

2. 左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**トランク構成**] をクリックします。

3. [**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。

4. 発信者番号のプレゼンテーションを構成するには、次のようにします。

   - エンタープライズ VoIP 展開で利用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、**[選択]** をクリックします。 [**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。

   - 新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。 新しいルールの定義の詳細については、「展開」のドキュメント  [の「翻訳](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) ルールの定義」を参照してください。

   - 既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。詳細については、「展開」のドキュメントの「[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)」を参照してください。

   - 既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。詳細については、「[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)」を参照してください。

   - トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。

     > [!CAUTION]
     > 関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。