---
title: Skype for Business Server で割り当てられていない番号範囲を作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Skype for Business Server Enterprise Voice のアナウンスメントアプリケーションで、割り当てられていない番号範囲を作成、変更、または削除します。 これは、割り当てられていない番号への通話の処理方法に影響します。
ms.openlocfilehash: f3d646e2d838312ee90453c66d1e7bf239cf1537
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233226"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Skype for Business Server で割り当てられていない番号範囲を作成または変更する
 
Skype for Business Server Enterprise Voice のアナウンスメントアプリケーションで、割り当てられていない番号範囲を作成、変更、または削除します。 これは、割り当てられていない番号への通話の処理方法に影響します。
  
Skype for Business Server を使用すると、組織で有効であるが、ユーザーまたは電話に割り当てられていない電話番号への着信通話に何が起こるかを確認できます。 そのような通話の処理を構成するには、割り当てられていない番号の表を設定します。 テーブルを使用して、通話をアナウンスメントアプリケーションまたは Exchange UM サーバーにルーティングすることができます。
  
割り当てられていない番号の表の構成方法はその使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を変更できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。
  
## <a name="configure-unassigned-phone-numbers"></a>割り当てられていない電話番号の構成

次のいずれかの手順を使用して、アナウンスメントアプリケーションの未割り当ての番号範囲を構成します。
  
> [!IMPORTANT]
> [割り当てられていない番号] テーブルを構成する前に、システムで既にお知らせを定義するか、Exchange ユニファイドメッセージング (UM) 自動応答を設定する必要があります。 
  
> [!TIP]
> ユーザーが割り当てられていない番号を呼び出した場合、Skype for Business Server は、未使用の番号テーブルを上から下に検索し、最初の一致する範囲を使用します。 したがって、最後の手段として実行される処理は、表の最終範囲に指定されている必要があります。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Skype for Business Server コントロールパネルを使用して、割り当てられていない電話番号を設定するには

1. RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。
    
4. [**割り当てられていない番号**] ページで、次のいずれかの操作を行います。
    
   - 新しい番号範囲を作成するには、[**新規**] をクリックします。[**名前**] にこの番号範囲の識別名を入力します。
    
     > [!NOTE]
     > 割り当てられていない番号の新しい範囲をデータベースに送信した後は、この名前を変更することはできません。 
  
   - 既存の番号範囲を変更するには、番号範囲の名前または名前の一部を検索フィールドに入力します。結果の番号範囲の一覧で、対象の名前をクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
5. 最初の [**数値の範囲**] フィールドに範囲の開始番号を入力し、2 番目の [**数値の範囲**] フィールドに範囲の終了番号を入力します。
    
   - 範囲の開始番号が終了番号より大きくならないようにしてください。
    
   - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。
    
   - 数値は正規表現 (tel:) に一致する必要があります。 (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})? これは、数値が文字列 "tel" で始まる可能性があることを意味します (文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、1 ~ 9 桁の数字です。 電話番号は最大17桁で、その後に形式の内線番号、内線番号、内線番号が続く場合があります。
    
6. [**アナウンス サービス**] で、次のいずれかの手順を実行します。 
    
   - [**アナウンス**] をクリックします。
    
   - [**Exchange UM**] をクリックします。
    
7. 前の手順で [**アナウンス**] をクリックした場合は、次の手順を実行します。
    
    a. [**宛先サーバーの FQDN**] で [**選択**] をクリックし、この範囲の未割り当て番号への着信通話を処理するアナウンスメントアプリケーションを実行するアプリケーションサービスのサービス ID をクリックして、[ **OK]** をクリックします。
    
    b. [**アナウンス**] で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。
    
8. 前の手順で [**Exchange UM**] をクリックした場合は、[**自動応答の電話番号**] で、[**選択**] をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、[**OK**] をクリックします。
    
9. [**OK**] をクリックします。
    
10. [**割り当てられていない番号**] ページで、割り当てられていない番号範囲が希望どおりの順序で並んでいることを確認します。表で範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックして、上矢印または下矢印をクリックします。
    
    > [!TIP]
    > Skype for Business Server は、割り当てられていない番号テーブルを上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。 重複する範囲があり、そのうちの 1 つが最後のアクションを指定している場合は、その範囲が一覧の一番下にあることを確認します。 
  
11. 割り当てられていない番号範囲が希望どおりの順序で並んでいることを確認したら、[**すべて確定**] をクリックします。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Skype for Business Server 管理シェルを使用して、割り当てられていない電話番号を設定するには

1. Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 新しい割り当てられていない番号範囲を作成するには、**New-CsUnassignedNumber** を使用します。 既存の割り当てられていない番号範囲を変更するには、**Set-CsUnassignedNumber** を使用します。
    
    > [!TIP]
    > 重複する範囲があり、それらを特定の順序で適用する場合は、Priority パラメーターを含めます。 最も優先度の高い範囲が通話に適用されます。 値0は、最も優先度の高い値を表します。
  
    コマンド ラインで、次のいずれかを実行します。
    
   - アナウンス サービスの番号範囲を作成するには、次のコマンドレットを実行します。
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Exchange UM 自動応答の番号範囲を作成するには、次のコマンドレットを実行します。
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     例:
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     または
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>未使用の番号範囲を削除する

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Skype for Business Server コントロールパネルを使用して、割り当てられていない番号範囲を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。
    
4. [**割り当てられていない番号**] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。
    
5. 結果の番号範囲の一覧で、名前をクリックして、[**編集**] をクリックし、[**削除**] をクリックします。
    
6. [**すべて確定**] をクリックします。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Skype for Business Server 管理シェルを使用して、割り当てられていない番号範囲を削除するには

1. Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンドラインで、次のように入力します。
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    次に例を示します。
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > その他のオプションの詳細については、「 [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)」を参照してください。 
  
## <a name="see-also"></a>関連項目

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
