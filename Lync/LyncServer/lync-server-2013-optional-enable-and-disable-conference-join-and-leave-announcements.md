---
title: 'Lync Server 2013: (オプション) 会議への入退出のアナウンスの有効化および無効化'
TOCTitle: (オプション) 会議への入退出のアナウンスの有効化および無効化
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48273589
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化

 

_**トピックの最終更新日:** 2012-09-30_

ダイヤルイン ユーザーが電話会議に出席または退席するとき、 会議アナウンス アプリケーションは、トーン音を再生するかユーザー名を発音することによって出席または退席をアナウンスできます。アナウンス方法はコマンドレットを実行することによって変更できます。このステップはオプションです。

## 会議への出退席のアナウンス方法を変更するには

1.  RTCUniversalServerAdmins グループのメンバーか、 **Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingConfiguration
    
    このコマンドレットを実行して、会議に参加するときに参加者が名前を記録する必要があるかどうかについての情報と、参加者がダイヤルイン会議に出席または退席するときの Lync Server の対応方法に関する情報を取得します。

4.  コマンド プロンプトで次のコマンドを実行します。
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   会議に出席する前に名前を記録するよう匿名参加者に依頼するかどうかを指定します。既定値は "$true" で、これは、会議に出席するときに名前を言うよう匿名参加者に求めることを意味します (認証された参加者の場合は、表示名が代わりに使用されるため、名前を記録しません)。
    
    **EntryExitAnnouncementsEnabledByDefault**   既定でアナウンス機能をオンまたはオフにするかどうかを示します。既定値は "$false" で、これは既定で、参加者が会議に出席または会議から退席するときにアナウンスが行われないことを意味します。ミーティング開催者は、ミーティングをスケジュールするときにこの設定を上書きできます。
    
    **EntryExitAnnouncementsType**   アナウンスが有効な会議に参加者が出席または退席するときに実行されるアクションを示します。既定値は "UseNames" で、これは、アナウンスをオンにすると、"Ken Myer が会議に参加しました" というようなアナウンスが行われることを意味します。
    
    これらの設定は、グローバル スコープまたはサイト スコープで構成できます。サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
    
    次に例を示します。
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    この例では、設定が Redmond のサイト スコープで定義されます。アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。参加者が会議に出席または会議から退席するときには、トーン音が再生されます。

