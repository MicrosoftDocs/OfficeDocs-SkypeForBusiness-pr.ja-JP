---
title: ホット デスク機能の有効と無効を切り替える
TOCTitle: ホット デスク機能の有効と無効を切り替える
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994057(v=OCS.15)
ms:contentKeyID: 52056654
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ホット デスク機能の有効と無効を切り替える

 

_**トピックの最終更新日:** 2013-02-20_

共通領域電話を、ホットデスク機能の電話としてセットアップできます。ホットデスク機能の電話は、ユーザーが各自のユーザー アカウントにログオンすることができる電話で、ログオン後は Lync Server の機能や各ユーザーのプロファイル設定が使用できます。ホット デスク機能は、クライアント ポリシーを使用して管理されます。ホット デスク機能の有効と無効を切り替えるには、共通領域電話によって使用されるクライアントポリシーを変更する必要があります。共通領域電話に割り当てられた会議ポリシーを確認する方法の詳細は、「[共通領域電話情報を表示する](lync-server-2013-view-common-area-phone-information.md)」を参照してください。

電話でホット デスク機能の有効と無効を切り替えるには、以下のように、EnableHotdesking パラメーターを指定して **New-CSClientPolicy** コマンドレットまたは **Set-CSClientPolicy** コマンドレットを使用します。これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行します。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。


## ホット デスク機能を有効にする

  - 共通領域電話のホット デスク機能を有効にするには、その電話 (または電話のコレクション) に割り当てられたクライアント ポリシーを変更する必要があります。
    
    変更する必要があるポリシーを識別した後で、EnableHotdesking パラメーターを True に設定した **Set-CsClientPolicy** コマンドレットを使用します。たとえば、次のようになります。
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 別の方法として、ホット デスク機能を有効にする新しいクライアント ポリシーを作成する目的で、**New-CsClientPolicy** コマンドレットを使用することもできます。たとえば、次のようになります。
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True


> [!IMPORTANT]
> このポリシーを作成した後で、適切な共通領域電話にそれを割り当てる必要があります。詳細は、「<A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">共有エリアの電話にポリシーを割り当てる</A>」を参照してください。



## ホット デスク機能を無効にする

  - 共通領域電話のホット デスク機能を無効にするには、**Set-CsClientPolicy** コマンドレットの EnableHotdesking パラメーターを既定値である False にリセットします。たとえば、次のようになります。
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

詳細については、[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) コマンドレットおよび [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) コマンドレットに関するヘルプ トピックを参照してください。

