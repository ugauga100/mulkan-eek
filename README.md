# mulkan-eek
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.enum.shapes import MSO_SHAPE
from pptx.dml.color import RGBColor

# Buat presentasi
prs = Presentation()
prs.slide_width = Inches(13.33)
prs.slide_height = Inches(7.5)

# Fungsi bikin teks dengan gaya warna-warni
def add_textbox(slide, text, left, top, width, height, font_size, font_color):
    box = slide.shapes.add_textbox(left, top, width, height)
    frame = box.text_frame
    frame.text = text
    p = frame.paragraphs[0]
    run = p.runs[0]
    run.font.size = Pt(font_size)
    run.font.bold = True
    run.font.color.rgb = font_color
    return box

# Slide 1 - "Oi Mulkan!"
slide1 = prs.slides.add_slide(prs.slide_layouts[6])
slide1.background.fill.solid()
slide1.background.fill.fore_color.rgb = RGBColor(255, 0, 0)  # Merah Boboiboy

add_textbox(
    slide1, "Oi Mulkan!", Inches(3), Inches(3), Inches(7), Inches(2),
    font_size=60, font_color=RGBColor(255, 255, 0)  # Kuning cerah
)

# Slide 2 - Foto "Palak awk"
slide2 = prs.slides.add_slide(prs.slide_layouts[6])
slide2.background.fill.solid()
slide2.background.fill.fore_color.rgb = RGBColor(0, 102, 204)  # Biru Boboiboy

add_textbox(
    slide2, "Palak awk", Inches(4.5), Inches(0.5), Inches(5), Inches(1.5),
    font_size=50, font_color=RGBColor(255, 255, 255)
)

# Ganti 'foto_kawan.jpg' dengan nama file asli foto kepala temanmu
image_path = "foto_kawan.jpg"
slide2.shapes.add_picture(image_path, Inches(4), Inches(2), height=Inches(4))

# Slide 3 - "Kok telele org ni"
slide3 = prs.slides.add_slide(prs.slide_layouts[6])
slide3.background.fill.solid()
slide3.background.fill.fore_color.rgb = RGBColor(255, 204, 0)  # Kuning Boboiboy

add_textbox(
    slide3, "Kok telele org ni", Inches(2), Inches(3), Inches(10), Inches(2),
    font_size=55, font_color=RGBColor(0, 0, 0)
)

# Simpan file PPT
prs.save("ppt_boboboi_meriah.pptx")
print("PPT berhasil dibuat: ppt_boboboi_meriah.pptx")
