---
title: Skype for Business のコールパーク範囲を作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Skype for Business Server Enterprise Voice のコールパークの範囲テーブルを作成または変更します。
ms.openlocfilehash: e4dc9e9384210ec2abcceb652b814aef8c401b05
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001727"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>Skype for Business のコールパーク範囲を作成または変更する

Skype for Business Server Enterprise Voice のコールパークの範囲テーブルを作成または変更します。

コールパークでは、orbits を使用してパーキング通話を行います。 ユーザーが通話をパークして取得するには、その前に、コールパークの軌道テーブルを構成する必要があります。 組織がパーキング通話のために予約する内線番号 (orbits) の範囲を指定し、各範囲に対してどのコールパークプールを処理するかを指定する必要があります。 軌道の範囲を定義する場合は、1つの軌道がすぐに再利用されることがないように、1つの orbits を使用することをお勧めします。ただし、ユーザーまたは他のサービスで使用可能な拡張機能の数を制限する orbits はあまり多くありません。 コールパークアプリケーションが展開されている Skype for Business Server プールごとに、複数のコールパークの範囲を作成することができます。 各 Call パーク範囲には、グローバルに一意の名前と一連の固有の拡張子を指定する必要があります。

> [!IMPORTANT]
> 一般的にオービット範囲には 100 未満のオービットが含まれます。1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。

オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。

> [!NOTE]
> コールパークの軌道テーブルでは、内側の市内ダイヤル (DID) 番号を軌道番号として割り当てることはできません。

コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Skype for Business Server コントロールパネルを使用して、駐車場で使用する電話番号の範囲を作成または変更するには

1. RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**Delegate Setup Permissions**」を参照してください。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。

4. [**コール パーク**] ページで、次のいずれかを実行します。

   - 新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。

     > [!NOTE]
     > オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。

   - 既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5. 最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。 注意:

   - 範囲の開始番号が終了番号より大きくならないようにしてください。

   - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

   - オービット範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

   - オービット範囲が文字\*または # で始まる場合、範囲は100よりも大きくなければなりません。

   - 有効な値: 正規表現文字列と一致する必要\\があります ([* | #]? [1 ~ 9] \d{0,7}) |([1-9] \d{0,8}) つまり、文字\*または # のいずれかから始まる文字列、または 1 ~ 9 の数値 (最初の文字はゼロにすることはできません) であることを意味します。 最初の文字が\*または # の場合、次の文字は 1 ~ 9 の数字にする必要があります (0 にすることはできません)。 後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば、"#6000"\*、"92000"\*、"95551212"、"915551212")。 最初の文字が "not \* " または "#" である場合、最初の文字は 1 ~ 9 の数字 (0 にすることはできません)、数字 0 ~ 9 (たとえば、"915551212"、"41212"、"300") でなければなりません。

   - プール当たりの合計が 50,000 オービットを超えないようにしてください。各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。

6. [**宛先サーバーの fqdn**] で、コールパークアプリケーションをホストするアプリケーションサービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。 オービット範囲の開始番号と終了番号で指定された範囲内の番号にパークされる通話は、すべてこのサーバーまたはプールにルーティングされます。

7. [**確定**] をクリックします。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>Skype for Business Server 管理シェルを使用してパーキング通話のための数値の範囲を作成または変更するには

1. Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「**代理人セットアップアクセス許可**」で説明するように、必要なユーザー権限を設定します。

2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

3. オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。 オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。

    コマンド ラインで、次のコマンドを実行します。

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    例:

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    次の例は、既存のオービット範囲内の番号を変更する方法を示しています。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>関連項目

[新規-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コールパークの範囲を削除する](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
