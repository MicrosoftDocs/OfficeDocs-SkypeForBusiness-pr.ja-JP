---
title: Skype for Business Server で割り当てられていない番号範囲を作成または変更する
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Skype for Business Server のアナウンス アプリケーションの割り当てられていない番号範囲を作成、変更、またはエンタープライズ VoIP。 これは、割り当てられていない番号の呼び出しの処理方法に影響します。
ms.openlocfilehash: 19a30aa4063f8ec0f4e890c4e244309347ed99c6
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711634"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Skype for Business Server で割り当てられていない番号範囲を作成または変更する
 
Skype for Business Server のアナウンス アプリケーションの割り当てられていない番号範囲を作成、変更、またはエンタープライズ VoIP。 これは、割り当てられていない番号の呼び出しの処理方法に影響します。
  
Skype for Business Server を使用すると、組織で有効なが、ユーザーまたは電話に割り当てられていない電話番号への着信呼び出しがどうなるかを示します。 このような呼び出しを処理するには、割り当てられていない番号テーブルを設定します。 この表を使用して、アナウンス アプリケーションまたは Exchange UM サーバーに通話をルーティングできます。
  
割り当てられていない番号の表の構成方法はその使用方法によって異なります。 組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。 割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。 有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。 テーブルに割り当てられていない拡張機能を含める場合は、特定の番号に対して発生するアクションを変更できます。 たとえば、顧客サービス デスクの内線番号を変更した場合は、テーブルに古い顧客サービス番号を含め、新しい番号を提供するアナウンスに割り当てできます。
  
## <a name="configure-unassigned-phone-numbers"></a>割り当てられていない電話番号を構成する

アナウンス アプリケーションの割り当てられていない番号範囲を構成するには、次のいずれかの手順を使用します。
  
> [!IMPORTANT]
> 割り当てられていない番号テーブルを構成する前に、お知らせが既に定義されている必要があります。または Exchange ユニファイド メッセージング (UM) を設定自動応答必要があります。 
  
> [!TIP]
> 割り当てられていない番号を呼び出す場合、Skype for Business Server は割り当てられていない番号テーブルを上から下に検索し、最初に一致する範囲を使用します。 したがって、最後の方法として実行するアクションは、テーブルの最後の範囲に対して指定する必要があります。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Skype for Business Server コントロール パネルを使用して割り当てられていない電話番号を構成するには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで、[音声機能] **をクリック** し、[割り当てられていない番号] **をクリックします**。
    
4. [割 **り当てられていない番号] ページ** で、次のいずれかの操作を行います。
    
   - 新しい番号範囲を作成するには、[新規] を **クリックします**。 [**名前**] に、この番号範囲の識別名を入力します。
    
     > [!NOTE]
     > 新しい割り当てられていない番号範囲をデータベースにコミットした後、この名前を変更することはできません。 
  
   - 既存の番号範囲を変更するには、検索フィールドに番号範囲の名前のすべてまたは一部を入力します。 結果の番号範囲の一覧で、必要な名前をクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。
    
5. 最初の **[数値の範囲]** フィールドに範囲の開始番号を入力し、2 番目の **[数値の範囲]** フィールドに範囲の終了番号を入力します。
    
   - 範囲の開始番号が終了番号より大きくならないようにしてください。
    
   - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。
    
   - 数値は正規表現と一致する必要があります `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 。 つまり、数値は文字列で始まる可能性があります (その文字列を指定しない場合は自動的に追加されます)、プラス記号 (+)、および数字 1 ~ `tel:` 9 です。 電話番号には最大 17 桁の数字を指定できます。その後に内線番号 ;ext= の後に内線番号を付けることもできます。
    
6. **[アナウンス サービス]** で、次のいずれかの手順を実行します。 
    
   - **[アナウンス]** をクリックします。
    
   - **[Exchange UM]** をクリックします。
    
7. 前の手順で **[アナウンス]** をクリックした場合は、次の手順を実行します。
    
    a. **[宛先サーバーの FQDN]** で、**[選択]** をクリックし、この割り当てられていない番号範囲への着信通話を処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID をクリックし、**[OK]** をクリックします。
    
    b. **[アナウンス]** で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。
    
8. 前の手順で **[Exchange UM]** をクリックした場合は、**[自動応答の電話番号]** で、**[選択]** をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、**[OK]** をクリックします。
    
9. **[OK]** をクリックします。
    
10. [割 **り当てられていない番号] ページ** で、割り当てられていない番号範囲が必要な順序で配置されます。 テーブル内の範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックし、上矢印または下矢印をクリックします。
    
    > [!TIP]
    > Skype for Business Server は、割り当てられていない番号テーブルを上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。 範囲が重なり合い、1 つの範囲が最後のリゾート アクションを指定する場合は、範囲がリストの下部に表示されます。 
  
11. 割り当てられていない番号範囲が必要な順序で設定されている場合は、[すべてコミット] **をクリックします**。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Skype for Business Server 管理シェルを使用して割り当てられていない電話番号を構成するには

1. 「代理セットアップのアクセス許可」の説明に従って、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でインストールされているコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. **New-CsUnassignedNumber** を使用して、割り当てられていない新しい番号範囲を作成します。 **Set-CsUnassignedNumber** を使用して、割り当てられていない既存の番号範囲を変更します。
    
    > [!TIP]
    > 範囲が重なり合い、範囲を特定の順序で適用する場合は、Priority パラメーターを指定します。 優先度が最も高い範囲が呼び出しに適用されます。 値 0 は、優先度が最も高い値を表します。
  
    コマンド ラインで、次のいずれかを実行します。
    
   - アナウンス サービスの番号範囲を作成するには、次のコマンドを実行します。
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - または、Exchange UM の番号範囲を作成するには、次自動応答実行します。
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     次に例を示します。
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     または
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     次の例は、割り当てられていない既存の番号範囲の数値を変更する方法を示しています。
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>指定されていない番号範囲を削除する

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Skype for Business Server コントロール パネルを使用して割り当てられていない番号範囲を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。
    
4. [**割り当てられていない番号**] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。
    
5. 結果の番号範囲の一覧で、名前をクリックして、[**編集**] をクリックし、[**削除**] をクリックします。
    
6. [**すべて確定**] をクリックします。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Skype for Business Server 管理シェルを使用して割り当てられていない番号範囲を削除するには

1. 「代理セットアップのアクセス許可」の説明に従って、Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または必要なユーザー権限でインストールされているコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. コマンドラインで、次のように入力します。
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    次に例を示します。
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > その他のオプションの詳細については [、「Remove-CsCallParkOrbit」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。 
  
## <a name="see-also"></a>関連項目

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
