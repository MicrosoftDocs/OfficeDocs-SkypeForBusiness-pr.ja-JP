---
title: アドレス帳管理用の New-CsClientPolicy
TOCTitle: アドレス帳管理用の New-CsClientPolicy
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48273949
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アドレス帳管理用の New-CsClientPolicy

 

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが New-CsClientPolicy コマンドレットを実行することを承認されています。 RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

New-CsClientPolicy コマンドレットにより、Lync Server 2013 で使用可能な機能にクライアントを備えさせるための数多くの設定を定義します。アドレス帳サービスの場合、関心の対象は AddressBookAvailability パラメーターです。 クライアントが利用できるオプションに直接影響するこのパラメーターには、次に示す 3 つの設定可能なオプションがあります。

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

定義すると、クライアントがアドレス帳にアクセスするときの方法が決まります。 このパラメーターを定義する場合は、オプションの 1 つを定義する必要があります。 この設定を変更しない場合は、既定の WebSearchAndFileDownload が有効なままになります。

次にその例を示します。

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

## 関連項目

#### その他のリソース

[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)

