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
description: Skype for Business Server のアナウンス アプリケーションの割り当てられていない番号範囲を作成、変更、または削除エンタープライズ VoIP。 これは、割り当てられていない番号への呼び出しの処理方法に影響します。
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837087"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Skype for Business Server で割り当てられていない番号範囲を作成または変更する
 
Skype for Business Server のアナウンス アプリケーションの割り当てられていない番号範囲を作成、変更、または削除エンタープライズ VoIP。 これは、割り当てられていない番号への呼び出しの処理方法に影響します。
  
Skype for Business Server を使用すると、組織で有効だが、ユーザーまたは電話に割り当てられていない電話番号への着信呼び出しに対する処理を指定できます。 このような呼び出しを処理するには、割り当てられていない番号の表を設定します。 この表を使用して、呼び出しをアナウンス アプリケーションまたは Exchange UM サーバーにルーティングできます。
  
割り当てられていない番号の表の構成方法はその使用方法によって異なります。 組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。 割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。 有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。 割り当てられていない内線番号を表に含める場合は、特定の番号に対して発生するアクションを変更できます。 たとえば、カスタマー サービス デスクの内線番号を変更する場合は、古い顧客サービス番号を表に含め、新しい番号を提供するアナウンスに割り当てできます。
  
## <a name="configure-unassigned-phone-numbers"></a>割り当てられていない電話番号を構成する

アナウンス アプリケーションの割り当てられていない番号範囲を構成するには、次のいずれかの手順を使用します。
  
> [!IMPORTANT]
> 割り当てられていない番号の表を構成する前に、システムでアナウンスが定義されている必要があります。または、Exchange ユニファイド メッセージング (UM) を設定自動応答があります。 
  
> [!TIP]
> 割り当てられていない番号に電話がかかっている場合、Skype for Business Server は割り当てられていない番号の表を上から下に検索し、最初に一致する範囲を使用します。 したがって、最後の方法として実行するアクションは、表の最後の範囲に対して指定する必要があります。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Skype for Business Server コントロール パネルを使用して割り当てられていない電話番号を構成するには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [音声機能] **をクリックし**、[割り当てられていない番号 **] をクリックします**。
    
4. [割 **り当てられていない番号] ページ** で、次のいずれかの操作を行います。
    
   - 新しい番号範囲を作成するには、[新規] を **クリックします**。 [**名前**] に、この番号範囲の識別名を入力します。
    
     > [!NOTE]
     > 新しい割り当てられていない番号範囲をデータベースにコミットした後、この名前を変更することはできません。 
  
   - 既存の番号範囲を変更するには、検索フィールドに番号範囲の名前のすべてまたは一部を入力します。 表示される番号範囲の一覧で、必要な名前をクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。
    
5. 最初の **[数値の範囲]** フィールドに範囲の開始番号を入力し、2 番目の **[数値の範囲]** フィールドに範囲の終了番号を入力します。
    
   - 範囲の開始番号が終了番号より大きくならないようにしてください。
    
   - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。
    
   - 数値は正規表現 (tel:)?( )と一致する必要 \+ があります。[1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. つまり、番号は tel という文字列で始まる可能性があります (その文字列を指定しない場合、自動的に追加されます)、プラス記号 (+)、および 1 ~ 9 の数字です。 電話番号は最大 17 桁で、その後に内線番号 ;ext= の後に内線番号を続けることもできます。
    
6. **[アナウンス サービス]** で、次のいずれかの手順を実行します。 
    
   - **[アナウンス]** をクリックします。
    
   - **[Exchange UM]** をクリックします。
    
7. 前の手順で **[アナウンス]** をクリックした場合は、次の手順を実行します。
    
    a.  **[宛先サーバーの FQDN]** で、**[選択]** をクリックし、この割り当てられていない番号範囲への着信通話を処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID をクリックし、**[OK]** をクリックします。
    
    b. **[アナウンス]** で、この割り当てられていない番号範囲に対して再生されるアナウンスをクリックします。
    
8. 前の手順で **[Exchange UM]** をクリックした場合は、**[自動応答の電話番号]** で、**[選択]** をクリックし、この割り当てられていない番号範囲に対して使用される電話番号をクリックし、**[OK]** をクリックします。
    
9. **[OK]** をクリックします。
    
10. [ **割り当て** られていない番号] ページで、割り当てられていない番号の範囲が必要な順序で並べ替えられていないか確認します。 テーブル内での範囲の位置を変更するには、範囲の一覧で 1 つ以上の連続する名前をクリックし、上矢印または下矢印をクリックします。
    
    > [!TIP]
    > Skype for Business Server は、割り当てられていない番号の表を上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。 重複する範囲を持ち、1 つの範囲で最後のアクションを指定する場合は、範囲がリストの一番下にある必要があります。 
  
11. 割り当てられていない番号範囲が必要な順序で表示されている場合は、[すべて確定] **をクリックします**。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Skype for Business Server 管理シェルを使用して割り当てられていない電話番号を構成するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」の説明に従って必要なユーザー権限を使用してログオン **します。**
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
3. **新しい割り当てられていない番号範囲を作成するには、New-CsUnassignedNumber** を使用します。 **既存の割り当てられていない番号範囲を変更するには、Set-CsUnassignedNumber** を使用します。
    
    > [!TIP]
    > 重複する範囲がある場合に、特定の順序で範囲を適用する場合は、Priority パラメーターを指定します。 最も優先度の高い範囲が呼び出しに適用されます。 値 0 は最高の優先度を表します。
  
    コマンド ラインで、次のいずれかの操作を行います。
    
   - アナウンス サービスの番号範囲を作成するには、次のコマンドを実行します。
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - または、Exchange UM メールボックスの番号範囲を作成するには自動応答実行します。
    
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

     次の例は、既存の割り当てられていない番号範囲の番号を変更する方法を示しています。
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>番号範囲を削除する

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Skype for Business Server コントロール パネルを使用して割り当てられていない番号範囲を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**割り当てられていない番号**] をクリックします。
    
4. [**割り当てられていない番号**] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。
    
5. 結果の番号範囲の一覧で、名前をクリックして、[**編集**] をクリックし、[**削除**] をクリックします。
    
6. [**すべて確定**] をクリックします。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Skype for Business Server 管理シェルを使用して割り当てられていない番号範囲を削除するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
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
