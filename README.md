pip install -r requirements.txt
DATABASE_URL=postgresql://user:password@localhost:5432/movie_db
alembic upgrade head
uvicorn app.main:app --reload
class Movie(Base):
    __tablename__ = "movies"

    id = Column(Integer, primary_key=True, index=True)
    title = Column(String, nullable=False)
    description = Column(Text, nullable=True)
    genre = Column(String, nullable=True)
    year = Column(Integer, nullable=True)
    rating = Column(Float, nullable=True)
