---
title: Skype for Business Online のコマンドレットと他の Windows PowerShell コマンドレットの組み合わせ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fd92d460ef79f7c4b201873db9a52b1a40c2a11
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Skype for Business Online のコマンドレットと他の Windows PowerShell コマンドレットの組み合わせ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-05_

Windows PowerShell を使用して Skype for Business Online に接続すると、約 40 Skype for Business Online のコマンドレットが使用できるようになります。 ただし、Skype for Business Online を管理している場合は、これらの40コマンドレットのみを使用するように制限されているわけではありません。 Skype for Business Online のコマンドレットに加えて、コンピューターにインストールされている他の Windows PowerShell コマンドレットを使うこともできます。 (Windows PowerShell 3.0 をインストールすると、数百種類の Windows PowerShell コマンドレットもインストールされます。)コマンドでは、Skype for Business Online のコマンドレットと、コンピューターで利用できるその他のコマンドレットを混在させることができます。

Windows PowerShell 3.0 の完全なコースはこの記事の範囲を超えていますが、コマンドレットを混在させて対応する理由を示すいくつかの例を次に示します。 まず、Skype for Business Online のコマンドレットには [印刷] コマンドが含まれていません。このコマンドは、Windows PowerShell コンソールでは見つかりません。 それでは、コマンドレットによって取得された情報の印刷イメージを取得するにはどうすればよいですか? 1つ目の方法は、情報を取得し、その情報を**Printer**コマンドレットに送信することです。

    Get-CsTenant | Out-Printer

追加のパラメーターは含まれていないため、 **Out-Printer**コマンドレットによって返されるすべての情報は、既定のプリンターに印刷されます。

同様に、Skype for Business Online のコマンドレットには、データをファイルに保存するためのパラメーターが含まれていません。 ただし、このコマンドでは、**出力ファイル**コマンドレットを使用して、返された情報をテキストファイル C\\:\\Logs: .txt に保存します。

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

このコマンドは、**オブジェクトの選択**コマンドレットを使って、画面に表示されるデータを制限します。 この例では、[ユーザーのアクセス](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15))コマンドレットを使用して、すべての Skype For business Online ユーザーに関する情報を取得し、次に**Select-Object**コマンドレットを使用して、表示するデータをユーザーの id 値とそのアーカイブポリシーに制限します。

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

コンピューターで使用できるコマンドレットは100個あるため、どのコマンドレットが Skype for Business Online のコマンドレットであり、どのコマンドレットも含まれていないかを判断するのが困難な場合があります。 Skype for Business Online のコマンドレット (および Skype for Business Online のコマンドレットのみ) の一覧を返すには、まず、すべての Skype for Business Online コマンドレットが含まれている一時的な Windows PowerShell モジュールの名前を特定する必要があります。 そのためには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-Module

次のような情報が画面に表示されます。

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

ModuleType スクリプトを持つモジュールは、Skype for Business Online のコマンドレットを含むモジュールです。 これらのコマンドレットのリストを返すには、モジュール名としてスクリプトモジュールの名前を使用して、 **Command**コマンドレットを実行します。

    Get-Command -Module tmp_5astd3uh.m5v

ModuleType と Script との間に等しい複数のモジュールが存在する可能性があります。 その場合は、次のコマンドを実行して、 **CsTenant**コマンドレットが含まれているモジュールを確認できます。

    Get-Command Get-CsTenant

**CsTenant**コマンドレットに対して返されるモジュールは、すべての Skype For business Online コマンドレットを含むモジュールになります。

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>関連項目


[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

