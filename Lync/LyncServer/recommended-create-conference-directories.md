---
title: (推奨) 会議ディレクトリを作成する
TOCTitle: (推奨) 会議ディレクトリを作成する
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63232661
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (推奨) 会議ディレクトリを作成する

 

_**トピックの最終更新日:** 2014-10-03_

会議ディレクトリには、Lync 2013 を使用している場合に参加者が会議に参加するために使用する英数字のミーティング ID と、ダイヤルイン会議の参加者が会議に参加するために使用する数字のみの電話会議 ID との間マッピングが保持されます。電話会議 ID の形式は次のとおりです。

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。 ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。 このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。 しかし、(すべてのプールでの) 会議ディレクトリの数が 9 よりも多くなると、会議 ID の長さは、追加の会議に対応するために長くなります。

## 会議ディレクトリを作成する

1.  Lync Server 管理シェル で、以下のコマンドレットを入力します:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    たとえば、以下では、ID が 42 で、プール atl-cs-001.litwareinc.com でホストされる会議ディレクトリが作成されます。:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## 関連項目

#### 概念

[Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)  

#### その他のリソース

[New-CsConferenceDirectory](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsConferenceDirectory)

