---
title: 'Lync Server 2013: ダイヤルイン会議のダイヤル プランの構成'
TOCTitle: ダイヤルイン会議のダイヤル プランの構成
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48273163
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成

 

_**トピックの最終更新日:** 2013-02-25_

ダイヤルイン会議を展開するときは、ダイヤルインのアクセス電話番号をルーティングするために、1 つ以上のダイヤル プランを作成または変更する必要があります。各ダイヤル プランの少なくとも 1 つの正規化ルールにより、内線電話番号が E.164 形式の完全な電話番号に変換されることを確認してください。ダイヤルイン会議のユーザーは、自分の暗証番号 (PIN) と電話番号を入力して、認証済みのエンタープライズ ユーザーとして会議に参加します。内線番号を完全な電話番号に変換する正規化ルールが必要なのは、内線番号だけの入力でユーザーを認証できるようにするためです。

ダイヤルイン会議のダイヤル プランをセットアップするには、次の作業を行います。

  - エンタープライズ VoIP を展開するかどうかに関係なく、グローバル ダイヤル プランを変更して、ダイヤルイン会議の地域を追加し、正規化ルールによりダイヤルイン アクセス番号が正確に変換されることを確認します。手順の詳細については、「[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

  - エンタープライズ VoIP が展開されていない場合は、ダイヤルイン会議へのアクセス電話番号に対するダイヤル プランを作成します。ダイヤルイン会議の地域を忘れないようにしてください。手順の詳細については、「[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)」を参照してください。

  - エンタープライズ VoIP が展開されている場合は、必要に応じて エンタープライズ VoIP を変更して地域を含め、ダイヤルイン アクセス番号のための適切な正規化ルールを使用します。手順の詳細については、「[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)」を参照してください。また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。手順の詳細については、「[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)」を参照してください。

地域の計画の詳細については、「計画」のドキュメントの「[Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)」を参照してください。

## このセクション中

  - [ダイヤル プラン情報の表示](lync-server-2013-view-dial-plan-information.md)

  - [Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)

  - [Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)

  - [Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)

