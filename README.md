# libarary-management
1.String bHql = "SELECT book FROM Book book WHERE book.publicationYear > :year";
List<Book> books = session.createQuery(bHql)
        .setParameter("year", 2010)
        .getResultList();


2.String bHql = "UPDATE Book book SET book.price = book.price * 1.1 WHERE book.author = :author";
  int updatedCount = session.createQuery(bHql)
        .setParameter("author", author)
        .executeUpdate();

4.Query query = session.createQuery("SELECT AVG(book.price) FROM Book book");
Double averagePrice = (Double) query.getSingleResult();

5.Query query = session.createQuery("SELECT author.name, COUNT(book) " +
                              	"FROM Author author " +
                              	"LEFT JOIN author.books book " +
                              	"GROUP BY author.id, author.name");
List<Object[]> result = query.getResultList();

6.Query query = session.createQuery("SELECT book " +
                              	"FROM Book book " +
                              	"JOIN book.author author " +
                              	"WHERE author.country = :countryName");
query.setParameter("countryName", "SpecificCountry");
List<Book> books = query.getResultList();

7.The author attribute in the Book entity is mapped as a many-to-one association with the @JoinColumn annotation specifying the foreign key column name (id).



