---
title: 'Lync Server 2013: 障害復旧時のアナウンスの管理'
TOCTitle: 障害復旧時のアナウンスの管理
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49887131
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での障害復旧時のアナウンスの管理

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 は、停止中の、割り当てなしの番号への通話に対するアナウンスをサポートします。停止中のアナウンス機能の復元は任意です。停止中にアナウンスを復元する場合は、バックアップ プールでアナウンス構成を再作成する必要があります。このセクションでは、障害復旧中にアナウンスを復元する場合に、何を行う必要があるかについて説明します。

このセクションの説明は、 アナウンス アプリケーションを使用する割り当てなしの番号範囲に適用されます。Exchange ユニファイド メッセージング (UM) 自動応答を使用する割り当てなしの番号範囲には適用されません。

## 停止前

停止中にアナウンスを使用するかどうかに関係なく、 アナウンス アプリケーションに対して構成したカスタマイズされたオーディオ ファイルがある場合は、そのバックアップを別途作成しておく必要があります。カスタマイズされたアナウンスは、 Lync Server 障害復旧プロセスの一部としてはバックアップされません。ファイルのバックアップを別途作成しておらず、サーバーにアップロードしたファイルが破損したり消去されたりした場合、ファイルは失われます。

カスタマイズされた音声ファイルのバックアップ コピーがなく、元のオーディオ ファイルが利用できなくなった場合は、当初ファイルをインポートしたサーバーまたはプールのファイル ストアを探すことで、アナウンス アプリケーションに対して構成したオーディオ ファイルを見つけることができます。アナウンス アプリケーションに対して構成したすべてのオーディオ ファイルは、ファイル ストアからコピーできます。

**ファイル ストアからオーディオ ファイルをコピーするには**

1.  コマンド ラインで、次のコマンドを実行します。
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    次に例を示します。
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    X-ApplicationServer-X は、プールのアプリケーション サーバーのサービス ID です (例: 1-ApplicationServer-1")


## 停止中

停止中に アナウンス アプリケーションを使用するには、このセクションで説明するタスクを実行して、バックアップ プールにアナウンス構成を再作成する必要があります。

> [!NOTE]
> 手順 2 を実行するとすぐに割り当てなしの番号範囲の所有権をバックアップ プールが取得するので、これらのタスクは、バックアップ プールへのフェールオーバー後に実行することをお勧めします。


> [!NOTE]
> この手順は、Exchange UM 自動応答の電話番号を使用する番号範囲については必要ありません。


**バックアップ プールでアナウンス構成を再作成するには**

1.  次の手順を実行して、プライマリ プールに展開したアナウンスをバックアップ プールに再作成します。
    
    1.  プライマリ プールで使用していたオーディオ ファイルがある場合は、 **Import-CsAnnouncementFile** コマンドレットを使用し、Parent パラメーターにバックアップ プールを指定して、そのオーディオ ファイルをバックアップ プールにインポートします。
    
    2.  **New-CsAnnouncement** コマンドレットを使用し、Parent パラメーターにバックアップ プールを指定して、個々のアナウンスを再作成します。
    
    > [!NOTE]
    > これらのパラメーターを使用してバックアップ プールにアナウンスを作成する方法の詳細については、「<a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でのアナウンスの作成</a>」を参照してください。


2.  すべてのアナウンスがバックアップ プールに再作成されたら、プライマリ プールでアナウンスを使用している割り当てなしの番号範囲をすべて、バックアップ プールに再作成したアナウンスに転送します。
    
    プライマリ プールでアナウンスを使用している割り当てなしの番号範囲ごとに、次のコマンドを実行します。
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

## 停止後

プライマリ プールが利用可能になったら、停止中に変更した割り当てなしの番号範囲を、再びプライマリ プールに転送する必要があります。

> [!NOTE]
> この手順は、Exchange UM 自動応答の電話番号を使用する番号範囲については必要ありません。


**プライマリ プールでアナウンスを復元するには**

1.  復旧中にプライマリ プールを再構築した場合は、バックアップ プールで実行したのと同様にオーディオ ファイルをインポートし、アナウンスを作成することによって、プライマリ プールにアナウンスを再作成する必要があります。ただし、この場合は Parent パラメーターにプライマリ プールを指定しません。詳細については、このトピックで前述した「停止中」のトピックを参照してください。

2.  停止中に変更した割り当てなしの番号範囲ごとに、次のコマンドを実行します。
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  必要に応じて、バックアップ プールに再作成したアナウンスを削除します。バックアップ プールの アナウンス アプリケーションに構成したアナウンスの一覧を取得するには、コマンド ラインで、次のコマンドを実行します。
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    次に例を示します。
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    結果の一覧で、削除するアナウンスを特定し、その GUID をコピーします。削除するアナウンスごとに、次のコマンドを実行します。
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    次に例を示します。
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


