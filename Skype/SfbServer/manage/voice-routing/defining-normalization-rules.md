---
title: Skype for Business Server で正規化ルールを定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server の正規化ルールは、.NET Framework 正規表現を使用して、ダイヤルされた電話番号を e.164 形式に変換します。言い換えると、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Skype for Business Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。
ms.openlocfilehash: 2fd7f59bcebcfe676a03ce5a6a897336551ddbad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151217"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Skype for Business Server で正規化ルールを定義する

Skype for Business Server の正規化ルールは、.NET Framework 正規表現を使用して、ダイヤルされた電話番号を e.164 形式に変換します。言い換えると、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Skype for Business Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、「[ダイヤルプランと正規化ルール](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)」を参照してください。

正規表現を記述する方法の詳細については、「 [.Net Framework 正規表現](https://go.microsoft.com/fwlink/p/?linkId=140927)」を参照してください。

正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。
- [**正規化ルールの構築**ツールを使用](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)して、先頭の数字、長さ、削除する数字、追加する数字の値を指定し、[Skype For Business Server] コントロールパネルで対応する一致パターンと変換ルールを生成できるようにします。
- [正規表現を手動で記述](#create-or-modify-a-normalization-rule-manually)して、照合パターンと変換ルールを定義します。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>正規化ルールの構築を使用して正規化ルールを作成または変更する

Skype for Business Server コントロールパネルで正規化ルールを作成または変更する場合は、次の手順を実行します。 

**[正規化ルールの構築] を使用してルールを定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「[委任のセットアップのアクセス許可](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)」を参照してください。
2. ブラウザーウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Install and open 管理ツール](../../management-tools/install-and-open-administrative-tools.md)」を参照してください。
3. オプション手順11で「 [Create a dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) 」の手順を実行するか、手順10で[ダイヤルプランを変更](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan)します。 
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。
6. [**正規化ルールの構築**] で、次のフィールドに値を入力します。
    - **先頭の数字**: (オプション) パターンと照合するダイヤル番号の先頭の桁数を指定します。 たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。
    - **長さ**: 照合パターンで桁数を指定し、パターンがこの長さと正確に一致するかどうか、またはこの長さ以上のダイヤル番号を一致させるか、または任意の長さのダイヤル番号と一致するかを選択します。
    - **削除する桁数**: (オプション) パターンと照合するダイヤル番号から削除する開始の桁数を指定します。
    - **追加する数字**: (オプション) パターンと照合するダイヤル番号に追加する数字を指定します。
    
    これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。 たとえば、**数字**を空白のままにしている場合は、 **[長さ**] フィールドに「 **7** 」を入力し **、[****削除する数字**] に**0**を指定すると、**一致するパターン**での正規表現の結果は次のようになります。

    **^ (\d{7}) $**

7. [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    - 一致パターンで指定した桁数を表す値。 たとえば、一致パターンが **^ (\d{7}) $** の場合、変換ルールの $1 は7桁のダイヤル番号を表します。
    - (オプション) [**追加する数字**] フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。
    
    たとえば、**宛先に一致するパターン**が、ダイヤル番号のパターンとして **^{7}(\d) $** を含んでいる場合、e.164 電話番号のパターンとして **+ 1425 $ 1**が**含まれて**いる場合、ルールは5550100から + 14255550100 に正規化します。

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。
    > [!Note] 
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「[音声ルーティングのテスト](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)」を参照してください。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。 
    > [!Note]
    > 正規化ルールを作成または変更するときにはいつでも、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「[保留中の変更を音声ルーティング構成に公開する](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)」を参照してください。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手動で正規化ルールを作成または変更する

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。

**正規化ルールを手動で定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「[委任のセットアップのアクセス許可](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)」を参照してください。
2. ブラウザーウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Install and open 管理ツール](../../management-tools/install-and-open-administrative-tools.md)」を参照してください。
3. オプション手順11で「 [Create a dial plan](GET LINK AFTER MIGRATION) 」の手順を実行するか、手順10で[ダイヤルプランを変更](GET LINK AFTER MIGRATION)します。  
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。
6. [**正規化ルールの構築**] で [**編集**] をクリックします。
7. [正規表現の入力] で次のように入力します。
    - [**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    - [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。

    たとえば、[**このパターンを照合**] に「 **^{7}(\d) $** 」と入力し、[**変換ルール**] に「 **+ 1425 $ 1** 」と入力すると、ルールは5550100から + 14255550100 に正規化されます。

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。

    > [!Note]
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「[音声ルーティングのテスト](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)」を参照してください。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [**ダイヤルプラン**] ページで、[ **commi**t] をクリックし、[**すべて確定**] をクリックします。 
