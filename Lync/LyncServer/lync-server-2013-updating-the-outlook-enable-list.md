---
title: Outlook の有効リストの更新
TOCTitle: Outlook の有効リストの更新
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48272220
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Outlook の有効リストの更新

 

_**トピックの最終更新日:** 2013-01-07_

Outlook のアドイン管理リストに含めるポリシーを作成することで、Microsoft Lync 2013 用オンライン ミーティング アドインがユーザーに対して常に有効になるように指定できます。これを行うには、アドイン管理リスト ポリシーを構成して、アドインが無効にならないようにし、ユーザーがこれを手動で無効にできないようにします。アドイン管理リスト ポリシーは、グループ ポリシー管理コンソールの Office 管理テンプレート ファイルに含まれています。これにより、レジストリ キーが HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList に作成されます。このキーに ucaddin.dll の値を追加して、アドインが常に有効になるように、また、ユーザーがこれを手動で無効にできないように ucaddin.dll 値を構成できます。

## ucaddin.dll を Outlook アドイン リストに追加するには

  - HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList にある AddinList レジストリ キーに、次の値を追加します。
    
      - レジストリ タイプ = REG\_SZ
    
      - 名前 = ucaddin.dll
    
      - 値 = 1 (アドインが常に有効になりエンド ユーザーが管理できないことを指定します)

