---
title: Skype for Business Server での正規化ルールの定義
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 正規化ルールでは、.NET Framework 正規表現を使用してダイヤルされた電話番号を E.164 形式に変換します。つまり、正規化ルールはユーザーによってダイヤルされた電話番号を受け取り、その番号を Skype for Business Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823377"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Skype for Business Server での正規化ルールの定義

Skype for Business Server 正規化ルールでは、.NET Framework 正規表現を使用してダイヤルされた電話番号を E.164 形式に変換します。つまり、正規化ルールはユーザーによってダイヤルされた電話番号を受け取り、その番号を Skype for Business Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、「ダイヤル プランと正規化 [ルール」を参照してください](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)。

正規表現を記述する方法の詳細については [、「.NET Framework の正規表現」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=140927)。

正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。
- [](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)正規化ルールの作成ツールを使用して、開始番号、長さ、削除する数字、および追加する数字の値を指定し、Skype for Business Server コントロール パネルで対応する一致パターンと変換ルールを生成します。
- [正規表現を手動で記述](#create-or-modify-a-normalization-rule-manually) して、一致パターンと変換ルールを定義します。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>[正規化ルールの作成] を使用して正規化ルールを作成または変更する

Skype for Business Server コントロール パネルで正規化ルールを作成または変更する場合は、次の手順を実行します。 

**[正規化ルールの構築] を使用してルールを定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「セットアップの [アクセス許可の委任」を参照してください](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. (省略可能)「手順 11[でダイヤル プランを作成する」または](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan)手順 10 でダイヤル プランを変更する手順に従います。 [](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) 
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。
6. [**正規化ルールの構築**] で、次のフィールドに値を入力します。
    - **開始番号**: (オプション) パターンに一致するダイヤル番号の先頭の数字を指定します。 たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。
    - **長** さ : 一致パターンの桁数を指定し、パターンをこの長さと正確に一致するか、この長さ以上のダイヤル番号と一致するか、任意の長さのダイヤル番号と一致するか選択します。
    - **削除する数字**: (オプション) パターンに一致するダイヤル番号から削除する開始番号の数を指定します。
    - **追加する数字**: (オプション) パターンに一致するダイヤル番号に追加する数字を指定します。
    
    これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。 たとえば、開始桁を空のままにした場合、[Length] フィールドに **「7」** と入力して[Exactly]を選択し、削除する桁数に **0** を指定すると、一致する **パターン** の正規表現は次のようになります。

    **^(\d {7} )$**

7. [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    - 一致パターンで指定した桁数を表す値。 たとえば、一致パターンが **^(\d {7} )$** の場合、変換ルールの $1 は 7 桁のダイヤル番号を表します。
    - (オプション) [**追加する数字**] フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。
    
    たとえば、一致するパターンにダイヤル番号のパターンとして **^(\d {7} )$** が含まれる場合、および変換ルールに E.164 電話番号のパターンとして **+1425$1** が含まれている場合、ルールは 5550100 を +14255550100 に正規化します。

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。
    > [!Note] 
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「音声ルーティングの [テスト」を参照してください](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。 
    > [!Note]
    > 正規化ルールを作成または変更するときにはいつでも、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「音声ルーティング [構成に保留中の変更を公開する」を参照してください](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>正規化ルールを手動で作成または変更する

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。

**正規化ルールを手動で定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「セットアップの [アクセス許可の委任」を参照してください](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. (省略可能)「手順 11[でダイヤル プランを作成する」または](GET LINK AFTER MIGRATION)手順 10 でダイヤル プランを変更する手順に従います。 [](GET LINK AFTER MIGRATION)  
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。
6. [**正規化ルールの構築**] で [**編集**] をクリックします。
7. [正規表現の入力] で次のように入力します。
    - [**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    - [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。

    たとえば、このパターンと一致するパターンに **^(\d {7} )$** を入力し、変換ルールに **+1425$1** を入力すると、ルールは 5550100 から +14255550100 に正規化されます。 

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。

    > [!Note]
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「音声ルーティングの [テスト」を参照してください](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [ダイヤル **プラン] ページで****[Commi t]** をクリックし、[すべて確定]**をクリックします**。 
