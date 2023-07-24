---
tag: [zotero, {{allTags}}]
aliases: {{citekey}}
authors: {{authors}}
status: 🟡
export: {{exportDate.format("DD/MM/YYYY")}}
url: {{url}}
ano: {{date.format("YYYY")}}
---


# Abstract

{{abstractNote}}

# {{title}}
{% for annotation in annotations -%}

{%- if annotation.colorCategory == "Yellow" -%}
	 - {{annotation.annotatedText }} [📃](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) 
 {%- endif -%}

{%- if annotation.colorCategory == "Red" -%}
	## {{annotation.annotatedText}} 
	{%- endif -%}
    {%- if annotation.colorCategory == "Magenta" -%}
      ### {{annotation.annotatedText}} 
	{%- endif -%}
     {%- if annotation.colorCategory == "Green" -%}
- % **"{{annotation.annotatedText}}"**  [📃](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) 

{%- endif -%}
    {%- if annotation.color== "#2ea8e5" -%} 
- @ **Rodapé**: {{annotation.annotatedText}}  [📃](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) 
{%- endif -%}
    {%- if annotation.imageRelativePath -%}
![[{{annotation. imageRelativePath}}]]  
{%- endif -%}


 {%- if annotation.colorCategory== "Orange" -%} 
- ! {{annotation.annotatedText}}  [📃](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})  #importante
{%- endif -%}

 {%- if annotation.color== "#a28ae5" -%} 
- # {{annotation.annotatedText}}  [📃](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
{%- endif %}
{% endfor -%}


# Referências úteis
{% for annotation in annotations -%}
  {% if annotation.colorCategory== "Gray" %} 
 - [ ] [[{{annotation.annotatedText}}]] #dicasLeitura 
{%- endif -%}
{% endfor -%}    

󠀠󠀠󠀠

# Anotações
{% for annotation in annotations -%}
{%  if annotation.comment %}
- \  {{annotation.comment}} [📃](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) 
 {%- endif -%}
{% endfor -%}

