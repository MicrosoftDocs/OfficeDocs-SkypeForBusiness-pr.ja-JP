---
title: 'Lync Server 2013: ダイヤル プランに地域が割り当てられていることの確認'
TOCTitle: ダイヤル プランに地域が割り当てられていることの確認
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48271848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 で、ダイヤル プランに地域が割り当てられていることの確認

 

_**トピックの最終更新日:** 2010-11-02_

ダイヤルイン会議で使用されるダイヤル プランでは、ダイヤルイン会議のアクセス番号と適切なダイヤル プランを関連付ける \[**ダイヤルイン会議の地域**\] が指定されている必要があります。 ダイヤル プランを設定する際に、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。 続いてダイヤルイン アクセス番号を作成する際に、そのアクセス番号と適切なダイヤル プランを関連付ける地域を選択します。

すべてのダイヤル プランに地域を指定することは重要であるため、この手順を使用して、すべてのダイヤル プランに地域があることを確認することをお勧めします。このステップはオプションです。

**Get-CsDialPlan** コマンドレットを使用して、すべてのダイヤルイン会議のダイヤル プランで地域が設定されているかどうかを確認します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 また、Lync Server コントロール パネルを使用して既存のダイヤル プラン内の地域を更新することもできます。Lync Server コントロール パネルの使用の詳細については、「[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

## ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    次に例を示します。
    
        Get-CsDialPlan
    
    この例では、組織で構成されているすべてのダイヤル プランが戻されます。

4.  戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。詳細については、Lync Server 管理シェルのドキュメントを参照してください。

## ダイヤル プランの地域プロパティを設定するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    次に例を示します。
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    この例では、Redmond という ID を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。詳細については、Lync Server 管理シェルのドキュメントを参照してください。

