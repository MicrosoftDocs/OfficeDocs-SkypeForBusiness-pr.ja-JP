---
title: ユーザーに対して Skype for Business 2015 クライアント環境の計画を立てる
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '概要: Skype for business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、または Lync Server 2010 を使用しているかどうかにかかわらず、新しい Skype for Business とユーザーの環境とユーザーの準備に必要な手順について説明します。'
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777752"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>ユーザーに対して Skype for Business 2015 クライアント環境の計画を立てる
 
**概要:** この更新プログラムについては、skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、または Lync Server 2010 を使用しているかどうかにかかわらず、新しい Skype for Business とユーザーの環境とユーザーの準備に必要な手順について説明します。
  
Lync 2013 用の2015年4月14日の Office 更新プログラムには、新しい Skype for Business ユーザーインターフェイスが含まれています。 この更新プログラムを使用すると、管理者はクライアントのルックアンドフィールを制御し、Lync 2013 クライアントの操作性を維持するか、強化された Skype for Business クライアントの操作性を使用するかを選択できます。 Skype for Business クライアントは Lync 2013 クライアントを実質的に置き換え、管理者が既存の Lync クライアントの機能と新しい Skype for Business クライアントの動作を選択できるようにする機能を追加しました。 この更新プログラムの詳細については、「 [2015 年4月14日、Lync 2013 用の更新プログラム (Skype For business)」 (KB2889923)](https://support.microsoft.com/kb/2889923/)を参照してください。
  
2015年5月12日に、更新された Skype for Business クライアントを含む、Office の月例の更新プログラムがもう1つあります。 4月の更新プログラムを適用しなかったお客様の多くは、Office 2013 の更新プログラム (12 月12日) を取得します。 このトピックの情報は、クライアントの更新のために組織、環境、およびユーザーを準備する際に役立ちます。 ユーザーやサポートチームにとって移行を簡単にするために、このトピックの情報を参考にして、ユーザーに対して使用するクライアントの操作性を決定し、組織内のクライアントの更新プログラムを展開する前に環境を変更してください。
  
- [ユーザーに対してどのようなクライアント環境を使用しますか?](user-experience.md#clientexperience)
    
- [Skype for Business クライアント用の環境を準備する](user-experience.md#usinglync)
    
- [サポートチームとエンドユーザーによる更新の準備に役立つリソース](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 クライアントの機能は、Skype for Business 2016 クライアントバージョンのオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成しようとする前に、クライアントバージョンをチェックして、番号16で始まらないことを確認してください。例: x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>ユーザーに対してどのようなクライアント環境を使用しますか?
<a name="clientexperience"> </a>

新しい Skype for Business クライアントを使用すると、ユーザーが Lync または Skype for business のいずれかを利用できるクライアントの操作を制御できます。 既定のクライアント環境は、Lync または Skype for Business のオンプレミスまたはオンラインを使用しているかどうかによって異なります。 今日の Microsoft 365 Apps for enterprise、Microsoft 365 Business Standard または Office 2013 で Skype for Business Online (Lync Online) を使用している場合は、更新された Skype for Business クライアントの操作性 (Skype のルックアンドフィールによる) が既定のユーザー環境になります。 現在、Lync Server をオンプレミスで使用している場合は、Lync クライアントの操作が既定で実行されます。
  
クライアントポリシーを使用して、ユーザーが取得するクライアント環境を構成できます。 クライアントポリシーは、Lync または Skype for business にログインしたときにユーザーに適用される構成設定のセットです。
  
### <a name="skype-for-business-client-experience"></a>Skype for Business クライアントの環境

Lync のすべての機能に加えて、Skype for Business には、シンプルなコントロールと、Skype の使い慣れたアイコンを備えた新しい機能が用意されています。 Skype for business の新機能の一部は、新しい Skype for Business クライアント環境でのみ利用可能です。 Skype for business の新機能の詳細については、「Skype for business の[探索](https://go.microsoft.com/fwlink/p/?LinkId=528686)」を参照してください。
  
### <a name="lync-client-experience"></a>Lync クライアントの環境

Lync クライアントの操作は、ユーザーが既に熟知している Lync 2013 クライアントの状態とよく似ていますが、ユーザーに知らせる変更点がいくつかあります。 Lync クライアント環境と Lync 2013 クライアントの相違点を確認するには、「 [lync を使用しているときに Skype For business が表示される](https://go.microsoft.com/fwlink/p/?LinkId=544712)のはなぜですか」と、このトピックで後述する追加のリンクを参照してください。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Skype for Business クライアント用の環境を準備する
<a name="usinglync"> </a>

クライアントの更新のために環境を準備するには、いくつかの作業を行う必要があります。 クライアント環境を構成するための変更を開始する前に、まず、クライアントポリシー設定をサポートしているバージョンの Skype for Business Server または Lync Server を使用していることを確認する必要があります。
  
クライアントの操作を制御するためのポリシー設定をサポートしているバージョンの Skype for Business Server または Lync Server を使用していることを確認したら、環境内のポリシー設定を構成する必要があります。 実行する必要のある具体的な手順は、使用している Skype for Business Server または Lync Server のバージョン、およびユーザーがオンプレミスであるかオンラインであるかによって異なります。 
  
クライアントの更新プログラムをユーザーに配信する前に、これらの変更を行う必要があります。これにより、ユーザーが Skype for Business クライアントを初めて起動したときからクライアントの操作を制御できるようになります。 次の表では、ユーザーに対して必要なクライアント環境を構成するために必要な手順について説明します。
  
|**展開**|**Skype for Business クライアントの環境**|**Lync クライアントの環境**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |クライアントビルド 4711.1002 (April、2015) 以降を展開する以外に、追加の手順はありません。  <br/> |[Lync クライアント環境で Skype for Business Online を使用する](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |クライアントビルド 4711.1002 (April、2015) 以降を展開する以外に、追加の手順はありません。  <br/> |[オンプレミスの Skype for Business Server で Lync クライアント環境を使用する](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 および Lync Server 2010  <br/> |[Lync Server 2013 または Lync Server 2010 で Skype クライアント環境を使用してオンプレミスで使用する](user-experience.md#SkypewithLynconprem) <br/> |[Lync Server 2013 または Lync Server 2010 で lync クライアント環境を使用してオンプレミスで使用する](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 で Skype クライアント環境を使用してオンプレミスで使用する
<a name="SkypewithLynconprem"> </a>

オンプレミス展開で Skype クライアントの操作を構成する場合は、このセクションの手順を実行します。 オンプレミスの既定の動作
  
 **手順 1:** 最初に、クライアントポリシー設定をサポートする Lync Server のバージョンを実行していることを確認します。
  
- **Lync server 2013** -lync server 2013 以降の更新プログラムについては、2014年12月の累積的な更新プログラム (5.0.8308.857) を実行している必要があります。 詳細については、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)」を参照してください。
    
- **Lync server 2010** -lync server 2010 以降の更新プログラムについては、2015年2月の累積的な更新プログラム (4.0.7577.710) を実行している必要があります。 詳細については、「 [Lync Server 2010 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)」を参照してください。
    
  **手順 2:** 次に、クライアントポリシーを使用して、skype for Business クライアントを使用して Skype クライアントの環境を設定します。 クライアントポリシーを使用してクライアント環境を設定するには、 **3 つのオプション**があります。
  
  **オプション 1:** グローバルポリシーを使用して、Skype クライアントの環境を設定します。 グローバルポリシーは、展開内のすべてのユーザーに適用されますが、グローバルポリシーよりもユーザーおよびサイトレベルのポリシーが優先されることに注意してください。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **オプション 2:** 環境で使用している既存のクライアントポリシーを変更して、Skype クライアントの動作を有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Skype クライアントの操作を割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **オプション 3:** Skype クライアント環境の設定を含む、ユーザーに割り当てる新しいポリシーを作成します。 最初に、新しいクライアントポリシーを作成し、 **id**パラメーターの値としてポリシーの名前を指定します。
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

次に、ポリシーの名前 ( **Identity**パラメーターに使用した値) を**PolicyName**パラメーターの値として使用して、ポリシーをユーザーに割り当てます。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **手順 3:** クライアントポリシーを構成したら、Skype for Business クライアント、ビルド 4711.1002 (April、2015) 以降を展開します。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Lync Server 2013 または Lync Server 2010 で lync クライアント環境を使用してオンプレミスで使用する
<a name="LyncwithLynconprem"> </a>

これは、オンプレミスの Lync Server 展開で Skype for Business クライアントが展開されるときの既定の動作です。 Lync クライアント環境を使用するようにクライアントポリシーを構成する必要はありませんが、クライアントの最初の実行動作を制御する必要がある場合があります。 既定では、ユーザーが Skype for business クライアントを初めて起動すると、Skype クライアント環境が使用され、Lync クライアントの動作を取得するためにクライアントを再起動するよう要求する通知がユーザーに表示されます。 ユーザーが初めてクライアントを起動したとき、およびクライアントコンピューターのシステムレジストリを変更してクライアントのチュートリアルをオフにしたときに、Lync クライアントの機能が表示されるように環境を構成することができます。 Skype for Business クライアントを展開する前に実行する必要のある手順については、以下のいずれかのトピックを参照してください。
  
- **Lync server 2013**については、「 [lync Server 2013 で Skype for business を使用してクライアント環境を構成する](https://go.microsoft.com/fwlink/p/?LinkId=532732)」を参照してください。
    
- **Lync server 2010** 「 [lync Server 2010 で Skype for business を使用してクライアント環境を構成する](https://go.microsoft.com/fwlink/p/?LinkId=532733)」を参照してください。
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>オンプレミスの Skype for Business Server で Lync クライアント環境を使用する
<a name="LyncwithSfBServer"> </a>

オンプレミスの Skype for Business Server 展開で Lync クライアントの環境を構成する場合は、このセクションの手順を実行します。
  
オンプレミス展開で Skype クライアントの操作を構成する場合は、このセクションの手順を実行します。 オンプレミスの既定の動作
  
 **手順 1:** 最初に、Skype for Business Server を展開します。
  
 **手順 2:** 次に、クライアントポリシーを使用して、Lync クライアント環境で Skype for Business クライアントを設定します。 クライアントポリシーを使用してクライアント環境を設定するには、 **3 つのオプション**があります。
  
 **オプション 1:** グローバルポリシーを使用して、Lync クライアントの環境を設定します。 グローバルポリシーは、展開内のすべてのユーザーに適用されますが、グローバルポリシーよりもユーザーおよびサイトレベルのポリシーが優先されることに注意してください。
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **オプション 2:** 環境で使用している既存のクライアントポリシーを変更して、Lync クライアントの動作を有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアントの操作を割り当てることができます。
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **オプション 3:** Lync クライアント環境の設定を含む、ユーザーに割り当てる新しいポリシーを作成します。 最初に、新しいクライアントポリシーを作成し、 **id**パラメーターの値としてポリシーの名前を指定します。
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

次に、ポリシーの名前 ( **Identity**パラメーターに使用した値) を**PolicyName**パラメーターの値として使用して、ポリシーをユーザーに割り当てます。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **手順 3: 省略可能。** 既定では、ユーザーが skype for business クライアントを初めて起動するときに、skype クライアント環境が使用され、ユーザーに対して Lync クライアントの動作を取得するためにクライアントを再起動するように求める通知が表示されます。 ユーザーが初めてクライアントを起動したときやクライアントのチュートリアルをオフにしたときに、クライアントコンピューターのシステムレジストリを変更することによって、Lync クライアントの機能が表示されるように環境を構成することができます。 Skype for Business クライアントを展開する前に実行する必要のある手順については、「 [skype for business でクライアント環境を構成](../../deploy/deploy-clients/configure-the-client-experience.md)する」を参照してください。
  
 **手順 4:** クライアントポリシーを構成したら、Skype for Business クライアント、ビルド 4711.1002 (April、2015) 以降を展開します。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Lync クライアント環境で Skype for Business Online を使用する
<a name="LyncwithSfBO"> </a>

Lync クライアントの操作を構成し、Skype for Business Online を使用している場合は、このセクションの手順を実行します。
  
Skype for Business Online を使用している場合でも、リモート PowerShell を使用してクライアントポリシーを構成することにより、組織内で Skype for business クライアントで Lync クライアントの機能を使用することができます。 クライアントポリシーを使用してクライアント環境を設定するには、 **3 つのオプション**があります。 ポリシー名とパラメーター名は、オンプレミスの Skype for Business または Lync Server を使用している場合に、クライアントの動作を構成するために使用する設定とは異なることに注意してください。
  
 **オプション 1:** グローバルポリシーを使用して、Lync クライアントの環境を設定します。 ユーザーに適用されるクライアントポリシーとサイトポリシーは、グローバルポリシーよりも優先されることに注意してください。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 2:** 環境で使用している既存のクライアントポリシーを変更して、Lync クライアントの動作を有効にする設定を含めます。 これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアントの操作を割り当てることができます。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **オプション 3:** Lync クライアント環境の設定を含むカスタムポリシーインスタンスを使用します。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

クライアントポリシーを構成したら、Skype for Business クライアント、ビルド 4711.1002 (April、2015) 以降を展開します。
  
Skype for Business Online でクライアント環境を構成する方法の詳細については、「Skype for business[と Lync クライアントのユーザーインターフェイスを切り替える](https://aka.ms/SfBOUI)」を参照して、最初の実行時の動作と PowerShell スクリプトを制御する方法についての手順を参照してください。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>サポートチームとエンドユーザーによる更新の準備に役立つリソース
<a name="support"> </a>

お客様の組織で移行を容易にするために、エンドユーザーの計画、教育、および参加に役立つその他のリソースが多数用意されています。
  
- [ビデオ: Skype for Business の概要](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business クイックスタートガイド (ダウンロード)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync が Skype for business に変更されました—新機能を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: 新しいユーザーのためのステップバイステップガイド](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Lync を使用しているときに Skype for Business が表示するのはなぜですか?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

