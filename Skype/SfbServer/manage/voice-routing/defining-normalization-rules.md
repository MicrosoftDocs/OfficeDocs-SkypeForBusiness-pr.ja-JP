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
description: Skype for Business Server 正規化ルールでは、.NET Frameworkを使用して、ダイヤルされた電話番号を E.164 形式に変換します。つまり、正規化ルールは、ユーザーがダイヤルした電話番号を受け取り、その番号を Skype for Business Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。
ms.openlocfilehash: 1be34e5c40a4da4e9def4de294ece134f2fe229d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120919"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Skype for Business Server での正規化ルールの定義

Skype for Business Server 正規化ルールでは、.NET Frameworkを使用して、ダイヤルされた電話番号を E.164 形式に変換します。つまり、正規化ルールは、ユーザーがダイヤルした電話番号を受け取り、その番号を Skype for Business Server で内部的に使用される形式に変換します。 各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、「ダイヤル プランと [正規化ルール」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules)。

正規表現の記述方法の詳細については、「正規表現」 [を参照.NET Frameworkしてください](/dotnet/standard/base-types/regular-expressions)。

正規化ルールを定義または編集するには、次のいずれかの方法を使用できます。
- [[正規化](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)ルールの作成] ツールを使用して、削除する開始数字、長さ、削除する数字、および追加する数字の値を指定し、対応する一致するパターンと変換ルールを Skype for Business Server コントロール パネルに生成します。
- [正規表現を手動で記述して](#create-or-modify-a-normalization-rule-manually) 、一致するパターンと変換ルールを定義します。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>正規化ルールのビルドを使用して正規化ルールを作成または変更する

Skype for Business Server コントロール パネルで正規化ルールを作成または変更する場合は、次の手順を実行します。 

**[正規化ルールの構築] を使用してルールを定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「セットアップの [アクセス許可を委任する」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールのインストールと開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. (省略可能)「手順 11[でダイヤル プランを作成](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan)する[](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan)」または「手順 10 でダイヤル プランを変更する」の手順に従います。 
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前 (たとえば、**5DigitExtension**) を入力します。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。
6. [**正規化ルールの構築**] で、次のフィールドに値を入力します。
    - **開始桁数**: (オプション) パターンに一致するダイヤル番号の先頭の数字を指定します。 たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425**」と入力します。
    - **長** さ : 一致するパターンの桁数を指定し、パターンをこの長さと正確に一致するか、少なくともこの長さのダイヤル番号と一致するか、任意の長さのダイヤル番号と一致するかどうかを選択します。
    - **削除する数字**: (オプション) パターンを一致するダイヤル番号から削除する開始桁数を指定します。
    - **追加する数字**: (オプション) パターンに一致するダイヤル番号に追加する数字を指定します。
    
    これらのフィールドに入力する値は、[**一致パターン**] および [**変換ルール**] に反映されます。 たとえば、開始桁数を空のままにした場合は、[長さ] フィールドに **7** と入力し、[厳密に] を選択し、[削除する桁数]に **0** を指定すると、一致するパターンの結果の正規表現は次のようになります。 

    **^(\d {7} )$**

7. [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    - 一致パターンで指定した桁数を表す値。 たとえば、一致するパターンが **^(\d {7} )$** の場合、変換ルールの $1 は 7 桁のダイヤル番号を表します。
    - (オプション) [**追加する数字**] フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425**」)。
    
    たとえば、一致するパターンにダイヤル番号のパターンとして **^(\d {7} )$** が含まれている場合、変換ルールに E.164 電話番号のパターンとして **+1425$1** が含まれている場合、ルールは 5550100 ~ +1425550100 を正規化します。

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。
    > [!Note] 
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「音声ルーティング [のテスト」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [**ダイヤル プラン**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。 
    > [!Note]
    > 正規化ルールを作成または変更するときにはいつでも、[すべて確定] コマンドを実行して構成の変更を公開する必要があります。 詳細については、「音声ルーティング [構成に保留中の変更を発行する」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration)。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>正規化ルールを手動で作成または変更する

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。

**正規化ルールを手動で定義するには**

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「セットアップの [アクセス許可を委任する」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)。
2. ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。 Skype for Business コントロール パネルを起動するために使用できるさまざまな方法の詳細については、「管理ツールのインストールと開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。
3. (省略可能)「手順 11[でダイヤル プランを作成](GET LINK AFTER MIGRATION)する[](GET LINK AFTER MIGRATION)」または「手順 10 でダイヤル プランを変更する」の手順に従います。  
4. [**新しい正規化ルール**] または [**正規化ルールの編集**] の [**名前**] に、正規化される番号のパターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension**」という名前を付けます)。
5. (オプション) [**説明**] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。
6. [**正規化ルールの構築**] で [**編集**] をクリックします。
7. [正規表現の入力] で次のように入力します。
    - [**このパターンを照合**] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    - [**変換ルール**] で、変換される E.164 電話番号の形式のパターンを指定します。

    たとえば、[このパターンの一致] に **^(\d {7} )$** を、変換ルールに **+1425$1** と入力すると、ルールは 5550100 から +14255550100 に正規化されます。  

8. (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、[**内線番号**] を選択します。
9. (オプション) 正規化ルールをテストする番号を入力し、[**次へ**] をクリックします。テスト結果は、[**テストする番号の入力**] の下に表示されます。

    > [!Note]
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。 詳細については、「音声ルーティング [のテスト」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)。 

10. [**OK**] をクリックして正規化ルールを保存します。
11. [**OK**] をクリックしてダイヤル プランを保存します。
12. [ダイヤル プラン **] ページで****、[Commi** t] をクリックし、[すべてコミット]**をクリックします**。