---
title: Lync Server 2010 会議ディレクトリを Lync Server 2013 に移動する
TOCTitle: 会議ディレクトリを移動する
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62388708
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議ディレクトリを移動する

 

_**トピックの最終更新日:** 2016-12-08_

プールを使用停止にする前に、Lync Server 2010 プール内の会議ディレクトリごとに以下の手順を実行する必要があります。

## 会議ディレクトリを Lync Server 2013 に移動するには

1.  Lync Server 管理シェルを開きます。

2.  組織の会議ディレクトリの ID を取得するには、次のコマンドを実行します。
    
        Get-CsConferenceDirectory
    
    上記のコマンドは、組織内のすべての会議ディレクトリを返します。そのため、使用が停止されているプールに結果を制限する必要がある場合があります。たとえば、完全修飾ドメイン名 (FQDN) が pool01.contoso.net のプールを使用停止している場合、次のコマンドを使用して返されるデータをこのプールからの会議ディレクトリ制限します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    このコマンドは、ServiceID プロパティに pool01.contoso.net という FQDN が含まれている会議ディレクトリのみを返します。

3.  会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    たとえば、会議ディレクトリ 3 を移動するには、次のコマンドを使用して Lync Server 2013 プールを TargetPool に指定します。
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    プール上のすべての会議ディレクトリを移動するには、次のようなコマンドを使用します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Lync 2010 プールを使用停止する手順を追った包括的な説明は、ドキュメント「Uninstalling Microsoft Lync Server 2010 and Removing Server Roles」を参照してください ([http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227) からダウンロード可能)。

会議ディレクトリを移動するときに、次のエラーが発生する可能性があります。

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

通常、このエラーが発生するのは、Lync Server 管理シェルがタスクを完了するための一連の更新された Active Directory アクセス許可を必要としている場合です。この問題を解決するには、管理シェルの現在のインスタンスを閉じて、シェルの新しいインスタンスを開いて、会議ディレクトリを移動するコマンドを再実行します。

