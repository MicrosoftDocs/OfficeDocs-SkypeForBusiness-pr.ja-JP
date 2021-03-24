---
title: Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '概要: 従来のクライアントで使用される個人用連絡先ストアを構成します。'
ms.openlocfilehash: 5f2131fd1e960e658d4257f0c86dd61a241aa499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109673"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 クライアント コンピューターで個人用連絡先ストアを構成する
  
Skype for Business Server 2015 および Exchange Server 2016 または Exchange Server 2013 を統合する場合は、クライアントが使用する個人用連絡先ストアを構成する必要があります。 特に、個人連絡先ストアとして Exchange を使用する Skype for Business を構成し、同時に、ユーザーが決定を上書きできないことを確認する必要があります。 これは、各クライアント コンピューターでレジストリ値を作成および構成することで実行できます。
  
> [!NOTE]
> 次の手順は、Lync 2010 クライアント以前を使用しているクライアントでのみ必要です。 Lync 2013 クライアントとすべての Skype for Business クライアントには、連絡先ストアの設定を上書きするオプションはありません。
  
ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。
  
1. クライアント コンピューターで、[スタート] をクリック **し、[実行** ] を **クリックします**。
2. [実行] **ダイアログ ボックス** に「regedit」と入力し、Enter キーを押します。
3. [レジストリ エディター] で、[ソフトウェア] HKEY_LOCAL_MACHINE展開し、[ポリシー] を展開し **、[Microsoft]** を展開し、[Communicator]**をCommunicator。**
4. 右クリックし **、[Communicator]** をポイント **し****、[DWORD (32 ビット) 値] をクリックします**。
5. 新しい値を作成した後、「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。
6. PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディタを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。 Windows 10 でこれを行う方法の詳細については、「グループ ポリシー オブジェクトの作成 [」の記事を参照](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) してください。
