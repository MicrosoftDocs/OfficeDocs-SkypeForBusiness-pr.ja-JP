---
title: Microsoft Teams でのコール パークおよび保留解除
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: コール パークを使用して取得し、Microsoft Teamsで通話を保留にする方法について説明します。
ms.openlocfilehash: eac146ee80624152e3f0be1ab2523f848328bb95
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605803"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams でのコール パークおよび保留解除

コール パークと取得は、ユーザーが通話を保留にできる機能です。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話をパークしたユーザーまたは他のユーザーは、サポートされているアプリまたはデバイスでそのコードを使用して通話を取得できます。 (詳細については、「[Teamsで通話をパーク](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)する」を参照してください)。

コール パークを使用する一般的なシナリオには、次のようなものがあります。

- 受付が、工場で働く人宛にかかってきた通話を保留にします。 次に、受付は場内アナウンス設備で着信とコード番号をアナウンスします。 通話を受けたユーザーは、工場のフロアで Teams 電話を取り、コードを入力して通話を保留解除できます。
- バッテリーの充電が切れかけているため、ユーザーが携帯電話で通話を保留にします。 その後、そのユーザーは Teams の卓上電話でコードを入力して通話を保留解除できます。
- サポート担当者が顧客からの電話を保留して、顧客への通話サポートを行うエキスパートへ Teams チャネルでアナウンスを送信します。 エキスパートが Teams クライアントにコードを入力し、通話を保留解除します。

通話をパークして取得するには、ユーザーがエンタープライズ VoIP ユーザーでなければならず、コール パーク ポリシーに含める必要があります。

> [!NOTE]
> コール パークと取得は、[Teams展開モードでのみ](teams-and-skypeforbusiness-coexistence-and-interoperability.md)使用でき、Skype for Business IP 電話ではサポートされていません。

## <a name="configure-call-park-and-retrieve"></a>コール パークを構成して取得する

コール パークを構成して取得するには、Teams管理者である必要があります。 既定では無効になっています。 コール パーク ポリシーを使用して、ユーザーに対して有効にしたり、ユーザー グループを作成したりできます。 一連のユーザーに同じポリシーを適用すると、そのユーザーの間で通話を保留したり、保留を解除したりできます。

既定では、通話ピックアップ番号の範囲は 10 ~ 99 です。 10 ~ 9999 の間で独自のカスタム範囲を作成することもできます。 最初にパークされた呼び出しは、範囲の開始 (たとえば 10) のピックアップ コードがレンダリングされます。 次にパークされた呼び出しでは、ピックアップ コードが 1 ずつインクリメントされてレンダリングされます。つまり、11 など、範囲の末尾がピックアップ コードとしてレンダリングされるまでです。 その後、レンダリングされたピックアップ コードは、範囲の先頭からもう一度やり直します。 

タイムアウトは、パークされた呼び出しがピックアップされていないときに呼び出し元に戻るまで待機する秒数として指定できます。 指定できる範囲は 120 ~ 1800 秒で、既定値は 300 秒です。

カスタム パーク範囲とパーク タイムアウトを設定するには、PowerShell モジュール 2.6.0 以降で使用できる New コマンドレットとSet-CsTeamsCallParkPolicy コマンドレットTeams使用します。 (カスタム パーク範囲とパーク タイムアウトの変更は、Teams管理センターでは管理できません。 Teams管理センターは引き続き既定値を表示します。

コール パーク ポリシーを有効にするには:

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceCall** >  **パーク ポリシー** に移動します。
2. [ **ポリシーの管理** ] タブで、[ **追加**] をクリックします。
3. ポリシーに名前を付け、[ **コール パークを許可する** ] を **[オン]** に切り替えます。 (通話のピックアップ範囲とタイムアウトはカスタマイズできません)。

    ![コール パーク ポリシー設定のスクリーンショット。](media/call-park-add-policy.png)

4. **[保存]** を選択します。

ポリシーを編集するには、一覧でポリシーを選択し、[ **編集]** をクリックします。

ポリシーを機能させるには、ユーザーに割り当てる必要があります。 [ポリシーは、ユーザーに個別に割り当てるか、グループに](assign-policies-users-and-groups.md)割り当てることができます。

グループにコール パーク ポリシーを割り当てるには

1. [ **コール パーク ポリシー** ] ページの [ **グループ ポリシーの割り当て** ] タブで、[ **グループの追加**] をクリックします。
2. 使用するグループを検索し、[ **追加**] をクリックします。
3. 他のグループ割り当てと比較してランクを選択します。
4. [ **ポリシーの選択]** で、このグループを割り当てるポリシーを選択します。

    ![パーク ポリシーイメージ。](media/call-park-assign-policy-to-group.png)

5. **[適用]** を選択します。

## <a name="related-topics"></a>関連項目

[Teamsで通話をパークする](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
