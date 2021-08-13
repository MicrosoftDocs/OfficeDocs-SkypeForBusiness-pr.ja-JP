---
title: コール パーク オービット範囲を作成または変更Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: コール パーク オービット範囲テーブルを作成または変更するには、Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 135a04d5e36a7a0590bd1809f8119360d549071627716605f7f7e13994561dbe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332009"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a>コール パーク オービット範囲を作成または変更Skype for Business

コール パーク オービット範囲テーブルを作成または変更するには、Skype for Business Server エンタープライズ VoIP。

コール パークは、駐車場の呼び出しにオービットを使用します。 ユーザーが通話をパークおよび取得する前に、コール パーク オービット テーブルを構成する必要があります。 組織がパーキング 通話用に予約する内線番号 (オービット) の範囲を指定し、各範囲を処理するコール パーク プールを指定して、それらの範囲のルーティングを定義する必要があります。 オービット範囲を定義する場合、目標は十分なオービットを使用して、1 つのオービットがあまり速く再利用されるのではなく、ユーザーや他のサービスで使用できる拡張の数を制限するほど多くのオービットを使用しすぎることです。 コール パーク アプリケーションが展開されている各プールSkype for Business Server複数のコール パーク オービット範囲を作成できます。 各 Call Park オービット範囲には、グローバルに一意の名前と一意の拡張機能セットが必要です。

> [!IMPORTANT]
> 一般的にオービット範囲には 100 未満のオービットが含まれます。 1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。 範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。

オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。

> [!NOTE]
> コール パーク オービット テーブルのオービット番号としてダイレクト インワード ダイヤル (DID) 番号を割り当てるのはサポートされていません。

コール パーク オービットの範囲を作成または変更するには、次のいずれかの手順を使用します。

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>コントロール パネルSkype for Business Serverを使用して、パーキング通話の番号の範囲を作成または変更するには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**音声機能**] をクリックし、[**コール パーク**] をクリックします。

4. [**コール パーク**] ページで、次のいずれかを実行します。

   - 新しいオービット範囲を作成するには、[**新規作成**] をクリックします。[**名前**] に、この番号範囲の識別名を入力します。

     > [!NOTE]
     > オービット範囲をデータベースにコミットした後に、この名前を変更することはできません。

   - 既存のオービット範囲を変更するには、検索フィールドにそのオービット範囲の名前または名前の一部を入力します。オービットの検索結果の一覧で、目的のオービットをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5. 最初の [**番号範囲**] フィールドに、このコール パーク オービットの内線番号の範囲の開始番号を入力し、2 番目の [**番号範囲**] フィールドに、範囲の終了番号を入力します。 次の点に注意してください。

   - 範囲の開始番号が終了番号より大きくならないようにしてください。

   - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

   - オービット範囲は一意である必要があります。 この範囲が他のどの範囲とも重ならないようにしてください。

   - オービット範囲が文字または #で始まる場合、範囲は 100 より大きい必要 \* があります。

   - 有効な値: 正規表現文字列と一致する必要があります ([ \\ *|#]?1-9]\d {0,7} )|([1-9]\d)。 {0,8} つまり、値は、文字または # で始まる文字列か、1 ~ 9 の数値である必要があります (最初の文字は \* 0 にすることはできません)。 最初の文字が #の場合、次の文字は 1 ~ 9 の数値 \* である必要があります (ゼロにすることはできません)。 後続の文字には、0 ~ 9 の任意の数字 \* ("#6000"、"92000"、"95551212"、"915551212" など) を \* 指定できます。 最初の文字がまたは #の場合、最初の文字は 1 から 9 の数字 (ゼロにすることはできません)、その後に最大 8 文字の数字 \* ("915551212"、"41212"、"300" など) が続きます。

   - プール当たりの合計が 50,000 オービットを超えないようにしてください。 各オービット範囲は、通常、100 以下のオービットを含みますが、10,000 オービットを超えなければ、範囲をそれよりも広くすることができます。 たとえば、開始番号 "7000000"、終了番号 "8000000" を指定するのではなく、開始番号 "7000000"、終了番号 "7000100" を指定することを検討してください。

6. **[宛先サーバーの FQDN]** で、コール パーク アプリケーションをホストするアプリケーション サービスの完全修飾ドメイン名 (FQDN) またはサービス ID をクリックします。 オービット範囲の開始番号と終了番号で指定された範囲の番号にパークされるすべての通話は、このサーバーまたはプールにルーティングされます。

7. **[確定]** をクリックします。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a>管理シェルSkype for Business Serverを使用して、パーキング通話の番号範囲を作成または変更するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、または「代理セットアップのアクセス許可」の説明に従って必要なユーザー権限でログオン **します。**

2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。

3. オービット番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。オービット番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。

    コマンド ラインで、次のコマンドを実行します。

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    次に例を示します。

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    次の例は、既存のオービット範囲内の番号を変更する方法を示しています。

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a>関連項目

[New-CsCallParkOrbit](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[Set-CsCallParkOrbit](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[コール パーク オービット範囲の削除](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)