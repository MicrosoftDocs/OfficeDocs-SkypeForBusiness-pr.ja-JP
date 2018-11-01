---
title: すべての Exchange UM 連絡先オブジェクトがレガシ プールから削除されたことを確認する
TOCTitle: すべての Exchange UM 連絡先オブジェクトがレガシ プールから削除されたことを確認する
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49886971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# すべての Exchange UM 連絡先オブジェクトがレガシ プールから削除されたことを確認する

 

_**トピックの最終更新日:** 2012-09-26_

Exchange UM 連絡先オブジェクトが従来の Office Communications Server 2007 R2 プールから削除されていることを確認するには、**OCSUmUtil** ツールまたは **Get-CsExumContact** コマンドレットを使用します。**OCSUmUtil** は次のフォルダーにあります。

%Program Files%\\Common Files\\ Lync Server 2013\\Support\\OcsUMUtil.exe

**OCSUmUtil** は、以下を持つユーザー アカウントを使用して実行する必要があります。

  - RTCUniversalServerAdmins および (Exchange Server ユニファイド メッセージング設定の読み取り権限が含まれる) RTCUniversalUserAdmins グループのメンバーシップ

  - 指定された組織単位 (OU) コンテナーに連絡先オブジェクトを作成するドメイン権限

**Get-CsExumContact** コマンドレットの使用方法の詳細については、Lync Server 管理シェルのドキュメントの「[Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact)」を参照してください。

