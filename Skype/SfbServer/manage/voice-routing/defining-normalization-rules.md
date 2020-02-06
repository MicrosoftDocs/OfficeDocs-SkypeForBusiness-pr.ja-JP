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
description: Skype for Business Server の正規化ルールは、ダイヤルした電話番号を E-164 形式に変換するために .NET Framework の正規表現を使用します。つまり、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Skype for Business Server で内部的に使用されている形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。
ms.openlocfilehash: ed9db264dc637251c535f111e419aac9aa0f5e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816997"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Skype for Business Server で正規化ルールを定義する

Skype for Business Server の正規化ルールは、ダイヤルした電話番号を E-164 形式に変換するために .NET Framework の正規表現を使用します。つまり、正規化ルールは、ユーザーがダイヤルした電話番号を取得し、その番号を Skype for Business Server で内部的に使用されている形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、「[ダイヤルプランと正規化ルール](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)」を参照してください。

正規表現の記述方法の詳細については、「 [.Net Framework の正規表現](http://go.microsoft.com/fwlink/p/?linkId=140927)」を参照してください。

正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。
- [ [**正規化ルールのビルド**] ツールを使用](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)して、開始番号、長さ、削除する数字、追加する数字の値を指定します。次に、Skype For business Server コントロールパネルで、対応する一致パターンと翻訳ルールを生成します。
- 一致するパターンと翻訳ルールを定義するために、[正規表現を手動で記述](#create-or-modify-a-normalization-rule-manually)します。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>正規化ルールを作成または変更する

Skype for Business Server コントロールパネルで正規化ルールを作成または変更する場合は、次の手順を実行します。 

**正規化ルールを作成してルールを定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「[委任のセットアップ権限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)」を参照してください。
2. ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 省略手順11で「[ダイヤルプランを作成](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan)する」または「[ダイヤルプランを変更](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan)する」の手順に従います。 
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号パターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。
6. [**正規化ルールの構築**] で、次のフィールドに値を入力します。
    - **開始**番号: (省略可能) パターンと一致させるダイヤル番号の先頭の数字を指定します。 たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。
    - [**長さ**]: 一致するパターンの桁数を指定し、パターンをこの長さと正確に一致させるか、またはダイヤルされた電話番号に一致するかどうかを選択します。
    - [**削除する数字**]: (省略可能) パターンと一致させる電話番号から削除する開始桁数を指定します。
    - **追加する数字**: (省略可能) パターンと一致させるダイヤル番号に追加する数字を指定します。
    
    これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。 たとえば、**数字**を空のままにしておく場合は **、[****長さ**] フィールドに「 **7** 」と入力して、**削除する数字**に**0**を指定すると、**一致するパターン**の正規表現は次のようになります。

    **^ (\d{7}) $**

7. [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    - 一致パターンで指定した桁数を表す値。 たとえば、対応するパターンが **^ (\d{7}) $** の場合、翻訳ルールの $1 は7桁のダイヤル番号を表します。
    - (オプション) "**追加する数字**" フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。
    
    たとえば、[**一致するパターン**] に **^ (\d{7})** という文字列が含まれている場合、ダイヤルする番号と**翻訳ルール**のパターンに **+ 1425 $ 1**が含まれていると、ルールは5550100から + 14255550100 を正規化します。

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。
    > [!Note] 
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳しくは、「[ボイスルーティングのテスト](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)」をご覧ください。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。 
    > [!Note]
    > 正規化ルールを作成または変更するときにはいつでも、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「[ボイスルーティング構成に保留中の変更を公開する](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)」を参照してください。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手動による正規化ルールの作成または変更

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。

**正規化ルールを手動で定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「[委任のセットアップ権限](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)」を参照してください。
2. ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。 Skype for Business コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。
3. 省略手順11で「[ダイヤルプランを作成](GET LINK AFTER MIGRATION)する」または「[ダイヤルプランを変更](GET LINK AFTER MIGRATION)する」の手順に従います。  
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号パターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、「5 桁の内線番号を変換」)。
6. [**正規化ルールの構築**] で [**編集**] をクリックします。
7. [正規表現の入力] で次のように入力します。
    - [**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    - [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。

    たとえば、"^ (\d) $" と入力すると、**翻訳ルール**の " **^ (\d{7}) $** " と **+ 1425 $ 1**と**入力した**場合、ルールは5550100から + 14255550100 に正規化されます。

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**実行**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。

    > [!Note]
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳しくは、「[ボイスルーティングのテスト](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)」をご覧ください。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [**ダイヤルプラン**] ページで、[ **commi**t] をクリックし、[**すべてコミット**] をクリックします。 
