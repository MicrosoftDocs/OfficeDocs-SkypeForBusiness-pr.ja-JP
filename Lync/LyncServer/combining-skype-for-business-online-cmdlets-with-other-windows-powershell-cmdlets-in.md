---
title: Skype for Business Online コマンドレットと他の Windows PowerShell コマンドレットの組み合わせ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7455ba7d98ecc11fcfc6e0c255eb430e213d3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Skype for Business Online コマンドレットと他の Windows PowerShell コマンドレットの組み合わせ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-05_

Windows PowerShell を使用して Skype for Business Online に接続すると、約40の Skype for Business Online コマンドレットを使用できるようになります。 ただし、Skype for Business Online を管理する場合は、これらの40コマンドレットのみを使用することに制限はありません。 Skype for Business Online のコマンドレットに加えて、コンピューターにインストールされている他の Windows PowerShell コマンドレットを使用することもできます。 (Windows PowerShell 3.0 をインストールすると、数百種類の Windows PowerShell コマンドレットもインストールされます。)コマンドでは、Skype for Business Online コマンドレットと、コンピューターで使用可能なその他のコマンドレットを混在させることができます。

Windows PowerShell 3.0 の完全なコースはこの記事の範囲を超えていますが、コマンドレットを組み合わせて使用する必要がある理由を示すいくつかの例を以下に示します。 最初に、Skype for Business Online コマンドレットには印刷コマンドは含まれていません。また、Windows PowerShell コンソールでこのコマンドは見つかりません。 では、コマンドレットによって取得された情報の印刷結果を取得するにはどうすればよいですか。 1つの方法として、情報を取得し、その情報を**プリンター**コマンドレットに送信する方法があります。

    Get-CsTenant | Out-Printer

追加のパラメーターは含まれていないため、**出力**コマンドレットによって返されるすべての情報が既定のプリンターに出力されます。

同様に、Skype for Business Online のコマンドレットには、データをファイルに保存するためのパラメーターが含まれていません。 しかし、このコマンドは次の**コマンドレットを使用して**、返された情報をテキストファイル C:\\Logs\\output.txt に保存します。

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

このコマンドは、**オブジェクトの選択**コマンドレットを使用して、返され、画面に表示されるデータを制限します。 この例[では、](https://technet.microsoft.com/library/JJ994026(v=OCS.15))すべての Skype For business Online ユーザーの情報を取得し、次に**オブジェクトの選択**コマンドレットを使用して、表示されるデータをユーザーの id 値とそのアーカイブポリシーに制限します。

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

コンピューター上で使用できるコマンドレットが数百あるため、Skype for Business Online コマンドレットとなっているコマンドレットを判別するのは困難な場合があります。 Skype for Business Online コマンドレット (および Skype for Business Online コマンドレットのみ) の一覧を取得するには、まず、すべての Skype for Business Online コマンドレットを含む Windows PowerShell の一時モジュールの名前を特定する必要があります。 そのために、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-Module

次のような情報が画面に表示されます。

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

ModuleType スクリプトを持つモジュールは、Skype for Business Online のコマンドレットを含むモジュールです。 これらのコマンドレットの一覧を取得するには、モジュール名としてスクリプトモジュールの名前を使用して、**コマンド**レットを実行します。

    Get-Command -Module tmp_5astd3uh.m5v

ModuleType がスクリプトと等しい複数のモジュールを持つことができます。 その場合は、次のコマンドを実行して、 **get-cstenant**コマンドレットが含まれているモジュールを調べることができます。

    Get-Command Get-CsTenant

**Get-cstenant**コマンドレットに対して返されるモジュールは、すべての Skype For business Online コマンドレットを含むモジュールになります。

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>関連項目


[Windows PowerShell と Skype for Business Online の概要](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

